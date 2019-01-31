# A tool to organize information in images and video

Images and videos can be tagged and objects in them can be measured.

Features
- Tag images and videos. Optionally specific areas.
- Add rulers over images. A line segment which starts at one point and ends at another.
- Rulers can be used to calculate the dimensions of objects on the same plane if one ruler is a known size.

## Storage
The tool stores data in a large JSON structure which is saved and can be committed to this project.

## Terminology
- Asset: An image or video.
- Tag: A searchable and relatable item. Ex: Room, Chair, etc
- Image Tag: An area of an image asset is related to a tag.
- Video Tag: A piece of video (start & end time) and optionally an area on that video is related to a tag.

## Structure
- tag { id, name, notes, child_tags }
- image { id, name, source, width, height, notes }
- image_tag { id, image_id, tag_id, notes, rect }
- video { id, name, source, width, height, framerate, length, notes }
- video_tag { id, video_id, tag_id, notes, start, end, start_rect, end_rect }
- ruler { id, name, notes, image_id, start_point, end_point, relative_to_ruler, relative_scale, measurement }
- ruler_tag { id, ruler_id, tag_id }
