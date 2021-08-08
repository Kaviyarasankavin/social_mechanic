# social_mechanic
Appliction
import google.assistant.embedded.v1alpha1.embedded_assistant_pb2

def generate_assist_requests():
    yield embedded_assistant_pb2.AssistConfig(
        audio_in_config=embedded_assistant_pb2.AudioInConfig(
            encoding='LINEAR16',
            sample_rate_hertz=16000,
        ),
        audio_out_config=embedded_assistant_pb2.AudioOutConfig(
            encoding='LINEAR16',
            sample_rate_hertz=16000,
        ),
        device_config=embedded_assistant_pb2.DeviceConfig(
            device_id=device_id,
            device_model_id=device_model_id,
        )
    )
    for data in acquire_audio_data():
        yield embedded_assistant_pb2.AssistRequest(audio_in=data)

