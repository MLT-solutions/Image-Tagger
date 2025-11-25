# **Image Tagger User Guide**

Welcome to the **Image Tagger** documentation. This tool allows you to bulk-embed titles and keywords into JPG images using a simple text matching system.

## **⚠️ Important Safety Warning**

Always work on copies of your images.  
This application writes directly to the metadata headers of your image files. While the process is safe, we recommend keeping a backup of your original photos before running bulk operations.

## **📋 1\. Preparing Your Data (Crucial Step)**

The application works by matching **Line 1** of your text file to **File 1** in your folder.

### **A. The Input Text File**

Create a standard .txt or .csv file using Notepad or Excel. Each line represents the metadata for one image (or one batch of images).

**The Format:**

Description Text Keywords: tag1, tag2, tag3, tag4

**Example File (input.txt):**

Golden retriever playing in the park Keywords: dog, puppy, grass, playing, happy  
Business meeting in a modern office Keywords: corporate, business, office, team, work  
Abstract blue geometric background Keywords: abstract, blue, background, texture, digital

### **🛑 Formatting Rules**

1. **The Separator:** You **MUST** use Keywords: (Capital 'K', colon at the end) to separate the title from the tags.  
2. **Case Sensitivity:** The separator is case-sensitive. keywords: or KEYWORDS: will **not** work.  
3. **Missing Separator:** If the app cannot find Keywords: in a line, it will take the **entire line** and use it as the Title (leaving the keywords blank).

### **B. The Image Folder**

* **File Type:** Currently supports .jpg and .jpeg.  
* **Sorting:** The app reads images in **Alphabetical Order**.  
* **Naming:** Rename your images sequentially to ensure they match your text file order (e.g., 001.jpg, 002.jpg, 003.jpg).

## **🖥️ 2\. Using the App**

### **Step 1: Select Inputs**

1. Launch **Image Tagger** from your Start Menu.  
2. Click **Browse CSV** to select your prepared text file.  
3. Click **Browse Folder** to select the folder containing your JPEGs.  
   * *(Pro Version)* Thumbnails will automatically load in the center panel.

### **Step 2: Configure Settings**

* **Batch Size (Pro Version Only):**  
  * **Set to 1 (Default):** 1 line of text \= 1 image.  
  * **Set to 4:** Line 1 of text is applied to images 1, 2, 3, and 4\. Line 2 is applied to images 5, 6, 7, and 8\.  
  * *Use Case:* Use batching when you have multiple variations of the same shot (e.g., a burst mode sequence) and want them all to have identical tags.

### **Step 3: Visual Review (Pro Version Only)**

Before processing, you can curate your images:

* **Navigation:** Use Arrow keys or click thumbnails to view images.  
* **Metadata Check:** The bottom-right panel shows the *current* EXIF data embedded in the file.  
* **Delete Bad Shots:** Press Del to permanently remove an image. The app will automatically adjust the index so your text file alignment stays correct.

### **Step 4: Execute**

Click **START TAGGING PROCESS** (or "EXECUTE PROCESS" in Lite).

* A progress bar will show the status.  
* **The Log File:** A metadata.csv report will be generated inside your image folder. This file contains a record of exactly what Title and Keywords were written to each filename.

## **🎨 3\. Pro Version Features & Hotkeys**

The Pro version includes a powerful image viewer and editor to help you cull images before tagging.

| Action | Shortcut / Mouse | Description |
| :---- | :---- | :---- |
| **Zoom In/Out** | Scroll Wheel | Zooms toward the mouse pointer position. |
| **Pan Image** | Click & Drag | Move around the image when zoomed in. |
| **Crop Mode** | Ctrl \+ X | Toggles the cropping crosshair cursor. |
| **Save Crop** | Ctrl \+ S | Overwrites the current file with the cropped selection. |
| **Delete** | Del | Deletes the file immediately. |
| **Fit to Screen** | Toolbar Button | Resets zoom level. |
| **1:1 View** | Toolbar Button | Views image at 100% scale. |

### **The Minimap**

When zoomed in, a small map appears in the bottom right corner.

* **Red Box:** Shows your current viewport.  
* **Click/Drag:** You can drag the red box on the minimap to quickly navigate large images.

## **❓ Troubleshooting**

**"List index out of range" Error**

* **Cause:** You have more images in the folder than lines of text in your input file.  
* **Fix:** Add more lines to your text file, or delete the extra images from the folder.

**"Keywords are appearing in the Title"**

* **Cause:** You likely typed keywords: (lowercase) or forgot the colon.  
* **Fix:** Ensure you use Keywords: exactly as shown in the examples.

**Metadata not showing in Windows Explorer**

* **Cause:** Windows Explorer sometimes caches old metadata.  
* **Fix:** Right-click the file \> Properties \> Details. If the data is there, it worked. Refreshing the folder often fixes the display.

**"Permission Denied"**

* **Cause:** The image is open in another program (like Photoshop).  
* **Fix:** Close all other image viewers and try again.
