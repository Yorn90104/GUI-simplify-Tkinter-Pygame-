# Base64 Asset Encoder and GUI Manager

## 簡介 | Introduction

此項目提供了一個基於 `Python` 的應用程序，包含以下功能：

This project provides a Python-based application with the following features:

1. **Base64 資源編碼器**：將圖片與音訊檔案轉換為 Base64 格式，並生成可直採導入的 Python 字典。
   **Base64 Asset Encoder**: Converts image and audio files into Base64 format and generates Python dictionaries for direct import.
2. **圖形用戶界面管理器**：使用 `Tkinter` 和 `Pygame` 提供 GUI 控制功能。
   **Graphical User Interface (GUI) Manager**: Provides GUI control features using `Tkinter` and `Pygame`.

項目包含兩個主要模組：
The project includes two main modules:
- `yieldb64.py`: 資源編碼器，處理圖片與音訊。
  `yieldb64.py`: An asset encoder that processes images and audio.
- `__init__.py`: GUI 管理程序，負責視窗、按鈕及音效控制。
  `__init__.py`: A GUI manager responsible for window, button, and sound control.

---

## 功能特色 | Features

### 1. Base64 資源編碼器 | Base64 Asset Encoder

- 自動檢測 `./Asset` 資料夾中的圖片與音訊檔案。
  Automatically detects image and audio files in the `./Asset` directory.
- 支援的圖片格式：`.jpg`, `.png`, `.ico` 。
  Supported image formats: `.jpg`, `.png`, `.ico`.
- 支援的音訊格式：`.wav` 。
  Supported audio format: `.wav`.
- 生成的 Base64 資源檔分別儲存於：
  Generated Base64 asset files are stored in:
  - `imageb64.py` (圖片字典 | Image dictionary)
  - `soundb64.py` (音訊字典 | Audio dictionary)

### 2. 圖形用戶界面管理器 | Graphical User Interface Manager

- **視窗管理 | Window Management**:
  - 設置視窗大小與標題。
    Sets window size and title.
  - 支援視窗圖標設定與臨時檔案管理。
    Supports window icon setting and temporary file management.

- **畫庫與框架 | Canvas and Frame**:
  - 提供多畫庫、多框架切換功能。
    Provides multi-canvas and multi-frame switching functionality.

- **按鈕與文字輸入 | Buttons and Text Input**:
  - 支援圖片與文字按鈕。
    Supports image and text buttons.
  - 提供文字輸入框管理。
    Provides text input box management.

- **圖片與文字操作 | Image and Text Operations**:
  - 圖片載入、更新。
    Loads and updates images.
  - 文字添加與更新。
    Adds and updates text.

- **音效與音樂控制 | Sound and Music Control**:
  - 解碼並播放 Base64 編碼的音效與音樂。
    Decodes and plays Base64-encoded sound effects and music.
  - 支援音效與背景音樂切換與控制。
    Supports switching and controlling sound effects and background music.

---

## 環境需求 | Requirements

- Python 3.8+
- 必須庫 | Required Libraries:
  - `tkinter` (標準庫，用於 GUI 開發 | Standard library for GUI development)
  - `Pillow` (用於圖像處理 | For image processing)
  - `pygame` (用於音訊播放 | For audio playback)

### 安裝 | Installation

1. 克隆此個仓庫：
   Clone this repository:
   ```bash
   git clone https://github.com/Yorn90104/GUI-simplify-Tkinter-Pygame-.git
   ```

2. 安裝依賴項：
   Install dependencies:
   ```bash
   pip install pygame pillow
   ```

---

## 使用範例 | Usage Examples

### 1. Base64 資源編碼器 | Base64 Asset Encoder

將圖片與音訊轉換為 Base64 格式：
Convert images and audio into Base64 format:

1. 將 `.jpg`, `.png`, `.ico`, 或 `.wav` 檔案放入 `./Asset` 資料夾。
   Place `.jpg`, `.png`, `.ico`, or `.wav` files into the `./Asset` folder.

2. 執行 `yieldb64.py`：
   Run `yieldb64.py`:
   ```bash
   python yieldb64.py
   ```

3. 檢查生成的 Base64 字典檔：
   Check the generated Base64 dictionary files:
   - 圖片的 Base64 字典：`./src/imageb64.py`
     Image Base64 dictionary: `./src/imageb64.py`
   - 音訊的 Base64 字典：`./src/soundb64.py`
     Audio Base64 dictionary: `./src/soundb64.py`

### 2. 圖形用戶界面管理器 | Graphical User Interface Manager

設置簡單 GUI 應用：
Set up a simple GUI application:

1. 創建一個 GUI 程序，導入 GUI 管理功能：
   Create a GUI program and import the GUI management functionality:
   ```python
   from __init__ import Window, Picture, Audio
   from src.imageb64 import image_dict
   from src.soundb64 import wav_dict

   class MyApp(Window):
       def __init__(self):
           super().__init__(title="測試應用", width=400, height=300)
           self.setup_frame_and_canvas("main", BG_pic=None)
           self.first_window("main")
           self.add_text("main", "Hello, 世界!", 200, 150, size=16, color="black")

   if __name__ == "__main__":
       app = MyApp()
       app.mainloop()
   ```

2. 保存檔案並執行：
   Save the file and execute:
   ```bash
   python my_app.py
   ```

3. 您將看到一個簡單的 GUI，顯示文字「Hello, 世界!」。
   You will see a simple GUI displaying the text "Hello, 世界!".

---

