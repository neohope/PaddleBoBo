How to build
============
### 1. install python 3.8

### 2. update pip
```shell
    python -m pip install --upgrade pip
```

### 3. create venv
```shell
# for windows
set PATH=D:/NeoLang/Python/Python38_x64;%PATH%
python -m venv venv
venv\\Scripts\\activate

# for linux
python -m venv venv
. venv/bin/activate
```

### 4. install packages
```shell
    pip install -r requirements.txt
```

### 5. clone code
```shell
git clone https://github.com/JiehangXie/PaddleBoBo
cd PaddleBobo
```

### 6. update default.yaml
```yaml
GANDRIVING:
  FOM_INPUT_IMAGE: './file/input/johncarmack.png'        #带人脸的静态图
  FOM_DRIVING_VIDEO: './file/input/zimeng.mp4'           #用作表情迁移的参考视频
  FOM_OUTPUT_VIDEO: './file/input/johncarmack.mp4'       #表情迁移后的视频输出路径

TTS:
  SPEED: 1.0    #语速
  PITCH: 1.0    #音高
  ENERGY: 1.0   #发音能级

SAVEPATH:
  VIDEO_SAVE_PATH: './file/output/video/'    #保存音频的路径
  AUDIO_SAVE_PATH: './file/output/audio/'    #保存生成虚拟主播视频的路径
```

### 7. generate virtual face
```shell
python create_virtual_human.py --config default.yaml
```

### 8. generate virtual video
```shell
#human，第3步生成的人脸视频路径
#output，生成虚拟主播视频的输出路径
#text，虚拟主播语音文本
from paddlespeech.utils.env import MODEL_HOME
python general_demo.py \
    --human ./file/input/johncarmack.mp4 \
    --output johncarmack_output.mp4 \
    --text "我是约翰卡马克，很高兴认识大家"
```

### 9. 原项目地址
 - https://github.com/JiehangXie/PaddleBoBo
