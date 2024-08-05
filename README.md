# keypoint-of-maize
Guidelines for Mechanical Weeding: Developing Weed Control Lines through Point Extraction at Maize Root Zones
Prior to introducing our method, to identify the most appropriate detection network for the maize seedling key point dataset, we initially evaluated three classical key point detection models within single-stage networks. These include YOLOPose, based on the YOLOv5pose key point detection model, and YOLOv7Pose, which utilizes YOLOv7-w6 as the foundational model with an additional key point layer designed to output human key points, as well as YOLOv8Pose. Table 1 and Fig. 1 illustrate the performance outcomes of these various models on the maize root key point dataset.
<img width="287" alt="table 1" src="https://github.com/user-attachments/assets/65cfc4ac-a73e-4bdc-85f2-6e16b44d5659">
The comparison table makes it clear that the performance gap in target detection within weeding zones among the three networks is minimal. Yet, YOLOv8Pose stands out for its precision and speed in identifying root key points. Considering the model's deployment on farm equipment and the premise that quicker detection speeds lead to better weeding outcomes, YOLOv8-Pose emerges as the optimal choice. As depicted in Fig. 1, its effectiveness in accurately predicting maize root key points and its adaptability for the initial stages of maize row line extraction underscore its suitability. Consequently, YOLOv8Pose is our preferred choice for the foundational detection model.
<img width="297" alt="figure2" src="https://github.com/user-attachments/assets/f31cadd5-3668-4a5c-a59f-2fbc28971bda">
After comparing the performance of these three models, YOLOv8Pose clearly leads in effectiveness, especially when looking at metrics like IoU and OCR. It reveals YOLOv8Pose's ability to accurately locate detection boxes while preventing unnecessary overlap. On the other hand, YOLO-Pose has its strengths in CR, yet it doesn't measure up as well in other areas, especially OCR, where its tendency for over-coverage could potentially harm the crops. YOLOv7-Pose is notable for its high IoU performance, ensuring that the detection boxes accurately cover the crop rows, but it falls a bit short in achieving optimal coverage rates. Considering the balance between accuracy, comprehensive coverage, and protecting the crops, YOLOv8Pose stands out as the most suitable choice for detecting targets in maize weeding zones for two-row maize setups.
<img width="303" alt="figure3" src="https://github.com/user-attachments/assets/fca5fd22-af5b-4d08-bf36-3fa9d75b4354">
The visualized outcomes of target and key point detection within the weeding region are presented in Fig. 3, illustrating the efficacy of different models across various environments. Regarding the target detection box, all three networks yield favorable results, effectively encompassing the central two rows of the maize area. However, YOLOv7Pose and YOLO-Pose exhibit tendencies toward over-coverage, implicating excessive inclusion of non-target zones in the weeding process, which adversely affects weeding efficiency and crop safety. YOLOv8Pose, conversely, demonstrates superior performance in terms of localization accuracy and optimal coverage frame alignment but also reveals instances of target area non-coverage, potentially resulting in overlooked weed removal. Within the realm of key point detection, although the precision of all three models leaves room for improvement, YOLOv8Pose's predictions are the most closely aligned with the actual root positions.
Integrating both the numerical data and visualization outcomes of the target detection frames, YOLOv8Pose is deemed more apt for the preliminary stage of maize row line extraction. Given that the risk of seedling injury presents a greater threat to crops than the potential for overlooked weed removal, YOLOv8Pose has been selected as our foundational detection model.

