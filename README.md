# Research-Project
## A Pre‐trained YOLO‐v5 model and an Image Subtraction Approach for Printed Circuit Board Defect Detection

## Purpose of this research 
  Almost every electronic product used regularly contains printed circuit boards, which are also used for security applications and for business purposes. Manual visual inspection of anomalies and faults in circuit boards during manufacture and usage is challenging. Due to a shortage of training data and the uncertainty of new abnormalities, identifying undiscovered flaws is complicated. The YOLO-v5 technique on a customized PCB dataset is used in the study to incorporate computer vision to detect six potential PCB defects. The algorithm is designed to be feasible, deliver precise findings, and operate at a considerable pace to be effective. Image subtraction technique is also implemented to detect flaws in printed circuit boards. The structural similarity index, a perception-based method, gauges how similar non-defective and defective PCB images are.

  ![image](https://github.com/richieaj/Research-Project/assets/87382894/61181b68-35c9-4fb0-8eb4-2773e277be51)

## Operations
A publicly available synthetic printed circuit board dataset, the HRIPCB [8] dataset, comprising 1386 photographs of six kinds of flaws, namely, missing holes, mouse bites, open circuits, short, spur, and spurious copper, created digitally on non-defective PCB images using AdobePhotoshop, was utilized in work. The dataset was used to train and validate the YOLO-v5 model. The annotations in the required format were also available with the dataset. To test and make predictions, actual PCB manufacturing sector data is also utilized, which had to be modified later to make accurate predictions.

## YOLO-V5

An equally sized grid structure is used by YOLO techniques to split up all the input pictures. Object detection is the task of every cell. Therefore, the bounding boxes for the spotted object are determined by those coordinates. The essential characteristics available for each box are the coordinates on the axes x and y, the aspect ratio of the entity, and a class probability indicating the likelihood that the object is contained in the box. The core components of YOLO v5, like all the previous single-stage object detector systems, are the head, neck, and backbone. The essential purpose of the backbone is to retrieve significant characteristics from an input picture. To extract valuable, important characteristics from an input picture in YOLO v5, the Cross Stage Partial Networks are employed as the backbone. The primary purpose of the neck is to produce feature pyramids. Feature pyramids enable systems to scale entities successfully in particular. Recognizing the same entity in various sizes and scales is beneficial. The final detecting step is mainly carried out using the head. The head uses anchor boxes on the attributes and produces final output vectors. The below figure provides the YOLO-v5 architecture comprising the model backbone, neck, and head.

![image](https://github.com/richieaj/Research-Project/assets/87382894/c94d04f6-04eb-4cbb-852c-d05720ee3b99)

## Results 
The validation of the YOLO-v5 model using the HRIPCB dataset produced appreciable outputs and the results are given in the below figures 

a) F1-score VS Confidence 

![image](https://github.com/richieaj/Research-Project/assets/87382894/3bc2ed46-39c2-411c-8818-e73873493cd2)   

b) Precision VS Confidence

![image](https://github.com/richieaj/Research-Project/assets/87382894/ff59ca04-ad5f-469a-8e75-6242a4fd541e)

c) Recall VS Confidence

![image](https://github.com/richieaj/Research-Project/assets/87382894/3cf61ff8-5918-4c73-917d-73ec04dab528)

The testing was initially done on several authentic nondefective PCB images to check whether the model worked well. The below shows that the results were not accurate enough since the model marked many areas as defective classes even on the non-defective board, which is an implication that the model is overfitted on the synthetic dataset and does not work well with real data

![image](https://github.com/richieaj/Research-Project/assets/87382894/0862a7bb-1181-4f39-b728-31c26bdd3771)

The next step to overcome the challenge was creating artificial defects on the real non-defective PCB images. The approach worked quite accurately since the model was also trained on digitally fabricated defects, and not real ones. Results from the image subtraction approach were moderately precise, and The structural similarity index measure could detect and draw bounding boxes over many of the defects. Still, the method cannot be considered very feasible. Fig. 8 shows the output obtained while using the image.

An observation that can be made from the outputs is that many defects are not detected and that many non defective areas have been detected as defective. The inference proves that both the approaches, the you-only-look-once algorithm, as well as the image subtraction technique, produces only moderately accurate results with real data. Additionally, two experiments were conducted in which different sets of reference and testing images were compared using the structural similarity index measure so that the faulty detection could be analyzed, considering SSIM as a factor.

![image](https://github.com/richieaj/Research-Project/assets/87382894/4726ede6-7a1a-4906-a899-4892ba98357c)

## Conclusion

The work uses two separate methods for finding anomalies on single-sided printed circuit boards: YOLO-v5 and an image subtraction approach. These techniques might be used to overcome the challenges associated with the manual examination of printed circuit board flaws. The YOLO-v5 model's flaw detection suggests that the model is overfitted since it performs exceptionally well on synthetic data but poorly on actual data. Due to the need for highresolution pictures in order to get accurate findings, the image subtraction approach utilized is likewise not particularly dependable. The fundamental issue is the scarcity of publicly accessible PCB industry data that is required. However, in terms of computing speed and training accuracy, YOLO-v5 may be regarded as an effective model for detecting printed circuit board defects.For improved performance and speed, future works could implement the most recent version of YOLO, such as the YOLO-v7 algorithm. Strategies to expand the amount of publicly available industry data might also be taken into consideration so that better accuracy could be achieved for defect detectors in printed circuit boards. Future efforts couldtake into account more varieties of flaws and early detectionas well.
