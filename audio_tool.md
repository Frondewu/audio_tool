# audio_tool
## CMUDict，输入单词，得到音素
```
cmu_dict = CMUDict('cmudict-0.7b')
print cmu_dict.lookup('hello')
```
## parselmouth调用praat接口
https://parselmouth.readthedocs.io/en/stable/api_reference.html
```
import parselmouth
sound = parselmouth.Sound(audio_path)
intensity = sound.to_intensity()
print(intensity.values)
pitch = sound.to_pitch()
pitch_values = pitch.selected_array['frequency']
```
## Pydub处理音频文件AudioSegment
https://github.com/jiaaro/pydub/blob/master/API.markdown
```
from pydub import AudioSegment
sound = AudioSegment.from_file(audio_path, format='wav')
print(sound.dBFS)
sound.export(new_audio_path, format='.wav')
```
静音检测，以1ms为窗长，得到该窗的分贝数，如果大于x1，认为有声，小于x2，认为静默，在x1和x2之间，且在左右一段时间分贝数超过x1，认为有声。
## kaldiio读ark文件
```
import kaldiio
array = kaldiio.load_mat(path)
```
