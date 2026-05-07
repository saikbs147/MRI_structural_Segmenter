---
name: mri-dicom-segmenter
description: Segments structural MRI DICOM files by their metadata, specifically grouping by Series Description to identify distinct anatomical structures or acquisition types within a study.
---

# MRI DICOM Segmenter

## Instructions

When the user wants to segment, group, or organize structural MRI DICOM files by their metadata:

1. Ask the user to select their DICOM files using the file picker (the skill handles this in the browser).
2. Call the `run_js` tool with the following exact parameters:
   - script name: index.html
   - data: A JSON string with the following field:
     - message: String. A short instruction string, e.g. "segment dicoms"

The script will open a file picker for the user to select DICOM files directly from their device, parse each file's binary metadata (without uploading anything), group them by the `SeriesDescription` DICOM tag (0008,103E), and display the results as an interactive grouped table in a webview.

Once the script returns its result, summarize what structures or series were found and how many files belong to each group.
