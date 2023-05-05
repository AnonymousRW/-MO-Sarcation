# MO-Sarcation
Your tone speaks louder than your face! Modality Order Infused Multi-modal Sarcasm Detection

For obtaining the data for the model, please follow the steps

Text data - It is available at https://github.com/soujanyaporia/MUStARD in data/sarcasm_data.json location. We also provide train, valid and text dlog ids with them.

Audio data - We first obtain raw video from https://github.com/soujanyaporia/MUStARD and convert those videos to audio format corresponding to the last utterance   of every dialog. The we proceed to obtain audio features in the same manner as described in https://github.com/thuiar/MIntRec/tree/main/tools/audio_preprocess.py

Video data - We get raws videos from https://github.com/soujanyaporia/MUStARD and obtain the video features corresponding to last utterance from https://github.com/soujanyaporia/MUStARD under Run the code section point 3 Download the pre-extracted visual features.

For running the model run the mo_sarcation.ipynb file.


Detailed steps: 

	1. First install the dependencies mentioned in the dependencies.txt.
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
