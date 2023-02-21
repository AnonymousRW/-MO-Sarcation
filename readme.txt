MO-Sarcation

Modality Order Infused Sarcasm Detection

To test the performance of the model on Mustard Dataset please follow the instruction

1. Make sure you have Nvidia A100 40GB GPU available.
2. Text file is taken from Mustard dataset. (https://github.com/soujanyaporia/MUStARD)
3. You have the following text file : json_file_fold.p
4. Extract Audio file from librosa 16,000 Hz and use last_hidden_state from wave2vec2 as audio features.
5. You have the following audio file : train_audio_fold_0.p and test_audio_fold_0.p
6. Video features provided in Github repo of Mustard dataset. (https://github.com/soujanyaporia/MUStARD)
7. You have the following video file : train_video_fold_0.p and test_video_fold_0.p
8. Your model will be saved in saved_model/best_case directory 
9. Run the mo_sarcation.ipynb file
10. For changing the audio video fusion layer in file mo_sarcation_audio_video.ipynb make changes inside the class MultiModalBartEncoder in the self.fusion_at_layer4, self.fusion_at_layer5 values in which layer  you want to insert audio and video.
11. bert_multimodal.ipynb and roberta_multimodal.ipynb have simple multimodal concatenation of modalities.

Test Results 

MO-Sarcation

Accuracy - 79.71
F1 - 0.7970

HKT (Our data split)

1. Make sure you have the following data split used in our case our_mustard_split_final.p
2. You have initialisation weights for acoustic, visual, hcf present in https://github.com/matalvepu/HKT
3. Run the hkt.ipynb file (Code taken from https://github.com/matalvepu/HKT and converted to jupyter notebook for running in Google Colab environment)

Accuracy - 72.00
F1 - 0.7201

