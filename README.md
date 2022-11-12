# Health monitoring system
Now-a-days health problems like cardiac failure, lung failures & heart related diseases are arising day by day at a very high rate. Due to these problems time to time health monitoring is very essential. A modern concept is health monitoring of a patient wirelessly. It is a major development in medical arena. Thus, paper based on the monitoring of the patient that is done by the doctor continuously without actually visiting the patient. Health professionals have developed a brilliant and inexpensive health monitoring system for providing more comfortable living to the people suffering from various diseases using leading technologies like wireless communications, wearable and portable remote health monitoring device. As a result, visits of doctors to the patients constantly are decreased as the information regarding patient's health directly reaches to doctor's monitor screen from anywhere the patient resides. Also, based on this doctor can save many lives by imparting them a quick & valuable service. In this, IoT is becoming a major platform for many services & applications, also using Raspberry Pi not just as a sensor node but also a controller here. Health Monitoring system using IOT describes the collection and interoperation of patient data collected from the sensors from the hospitals through IOT Technology. The collected sensor data will support the doctor in the emergency situation for the betterment and improvement of patient health. The hardware platform to implement the project consists of a sensor and Raspberry Pi 3B+ Model equipped in a way to communicate with a doctor through the Internet and Smart Phone. This proposed idea will help doctors to know about the 
state of patient health and monitor anywhere in the world.
 People who have to be under regular supervision with respect to heart function and other related factors, people living in rural areas especially can't afford to go to doctor, visiting cities.Hence the Health Monitoring system plays a significant in hand and help solving the major issues at during emergency.
 In this project we have included the heart rate and blood pressure monitoring by making use of the ppg pulse and developing algorithm and training the PPG – BP datasets to achieve a best comparative regressor model that performs well with the real time applicational use.
 
 ![image](https://user-images.githubusercontent.com/87423535/201459800-648f42a6-74f8-4e8d-a6ef-d4405c44d2f2.png)
 
 #PPG SIGNAL
Photoplethysmography (PPG) is an uncomplicated and inexpensive optical measurement method that is often used for heart rate monitoring purposes. PPG is a non-invasive technology that uses a light source and a photodetector at the surface of skin to measure the volumetric variations of blood circulation. PPG signal’s second derivative wave contains 
important health-related information.

![image](https://user-images.githubusercontent.com/87423535/201459905-035c2682-62b1-40b8-8c37-cb56f48953d7.png)

The PPG waveform comprises a pulsatile ('AC') physiological waveform attributed to 
cardiac synchronous changes in the blood volume with each heartbeat, and is superimposed 
on a slowly varying ('DC') baseline with various lower frequency components attributed to 
respiration, sympathetic nervous system activity and thermoregulation. Although the origins 
of the components of the PPG signal are not fully understood, it is generally accepted that 
they can provide valuable information about the cardiovascular system. There has been a 
resurgence of interest in the technique in recent years, driven by the demand for low cost, 
simple and portable technology for the primary care and community based clinical settings, 
the wide availability of low cost and small semiconductor components, and the advancement 
of computer-based pulse wave analysis techniques.

#MAX30102
Maxim Integrated MAX30102 Sensor is a highly integrated pulse oximetry and heart rate monitor module. The MAX30102 includes internal LEDs, photodetectors, optical 
elements, and low-noise electronics with ambient light rejection. This highly sensitive device 
operates on a single 1.8V power supply and a separate 5.0V power supply for the internal 
LEDs. Communication is through a standard I2C-compatible interface. This sensor can be shut 
down through software with zero standby current, allowing the power rails to remain powered 
at all times.


![image](https://user-images.githubusercontent.com/87423535/201459984-17880adf-3ed4-4262-be8c-3f39b4ebe349.png)


# BLOCK DIARGAM OF THE PROPOSED SYSTEM


![image](https://user-images.githubusercontent.com/87423535/201459999-41927eac-bff4-4aba-b06a-a7eeb4fded11.png)


#Heart Rate
Heart rate is calculated by counting the number of systolic peaks per minute.

![image](https://user-images.githubusercontent.com/87423535/201460031-ddb9f752-fdf3-47d9-913d-75c5353577fc.png)


# Extraction of the signal from the MAX30102 Sensor via Rasberry PI
The MAX30102 works by shining both lights onto the finger or earlobe (or essentially 
anywhere where the skin isn’t too thick, so both lights can easily penetrate the tissue) and 
measuring the amount of reflected light using a photodetector. This method of pulse 
detection through light is called Photoplethysmogram.

![image](https://user-images.githubusercontent.com/87423535/201460103-3c8cd24d-6bbf-49e4-8142-cddb52d389aa.png)

The oxygenated hemoglobin (HbO2) in the arterial blood has the characteristic of absorbing 
IR light. The redder the blood (the higher the hemoglobin), the more IR light is absorbed. As 
the blood is pumped through the finger with each heartbeat, the amount of reflected light 
changes, creating a changing waveform at the output of the photodetector. As you continue 
to shine light and take photodetector readings, you quickly start to get a heart-beat (HR) 
pulse reading.

![image](https://user-images.githubusercontent.com/87423535/201460122-4893725f-488a-4c6b-90ac-e4e3ffde056c.png)

#PPG CLEANING 

![image](https://user-images.githubusercontent.com/87423535/201460134-8bf66a10-6e37-4c21-9783-7386d1278828.png)

![image](https://user-images.githubusercontent.com/87423535/201460142-d0905155-3436-41aa-a20d-29cd15717803.png)


#BP
Blood pressure (BP), also referred to as Arterial blood pressure (ABP), is the pressure exerted 
by circulating blood upon the walls of blood vessels.
Datasets 
The blood pressure dataset provides clean and valid signals for designing cuff-less blood 
pressure estimation algorithms. The matlab files (.mat) contain raw electrocardiogram (ECG), 
photoplethysmography (PPG), and arterial blood pressure (ABP) signals stored as cell 
arrays of matrices where each cell is one record part. In each matrix, each row corresponds 
to one signal channel:
1: PPG signal, FS=125Hz; photoplethysmography from fingertip
2: ABP signal, FS=125Hz; invasive arterial blood pressure (mmHg)
3: ECG signal, FS=125Hz; electrocardiogram from channel II
Each cell is a record. There might be more than one record per patient (which is not possible 
to distinguish). However, records of the same patient appear next to each other. n-fold cross 
test and train is suggested to reduce the chance of train set being contaminated by test 
patients.
BP signals are extracted from the mat file and store them in an array/list. Systole and 
diastole are two phases of a heart beat. BP increases as the heart muscle contracts during 
systole, where blood is pushed towards the periphery of the body and it decreases when the 
heart relaxes to fill with blood during the diastole. Hence we take max(BP) to derive SBP and 
min(BP) to get DBP.

![image](https://user-images.githubusercontent.com/87423535/201460171-6584ff30-5ef7-4daf-b189-6de1f420d8aa.png)








