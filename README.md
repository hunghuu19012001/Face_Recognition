
Nhận diện khuôn mặt khá chuẩn xác bằng MTCNN và Facenet!
0.tải model chỉ lấy file - tạo folder Models trong FaceRecognitionMtcnnFacenet rồi bỏ vào 
https://drive.google.com/file/d/1EXPBSXwTaqrSC0OhUdXNmKSh9qJUQ55-/view
Cách chạy
1: Chụp mỗi người 10 tấm, tạo folder tên người trong dataset-face-raw
2. cắt khuôn mặt từ ảnh
python src/align_dataset_mtcnn.py  Dataset/FaceData/raw Dataset/FaceData/processed --image_size 160 --margin 32  --random_order --gpu_memory_fraction 0.25
3. train 
python src/classifier.py TRAIN Dataset/FaceData/processed Models/20180402-114759.pb Models/facemodel.pkl --batch_size 1000
4. final
python src/face_rec_cam.py 
import video thì python src/face_rec.py --path video/camtest.mp4 