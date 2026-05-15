# 📷 Instagram — 사용자가 직접 작성한 리뷰/댓글을 분석하고, 가장 인기를 끌어올 수 있는 방식으로 해시태그 및 게시 시간 변경

<create_file path="sessions/2026-05-15T07-35/youtube.md">```yaml
---
title: "Review & Comment Analysis & Hash Tag & Posting Time Adjustment"
description: "Analyze and adjust hashtags and posting time for the most popular reviews and comments."
---

### **Step 1: Retrieve Recent Reviews and Comments**

#### Command:
```bash
run_command "youtube search --channel $YOUTUBE_CHANNEL_ID --max-results 10 --order date --part snippet,comments"
```

**Expected Output:**
```
{
  "kind": "youtube#searchListResponse",
  "etag": "\"YOUR_E_TAG\"",
  "pageInfo": {
    "totalResults": 10,
    "resultsPerPage": 10
  },
  "items": [
    {
      "kind": "youtube#video",
      "id": "VIDEO_ID_1",
      "snippet": {
        "title": "Review 1",
        "description": "This is a sample review.",
        "publishedAt": "2023-04-01T12:34:56.000Z"
      },
      "comments": [
        {
          "kind": "youtube#comment",
          "id": "COMMENT_ID_1",
          "snippet": {
            "text": "This is a sample comment.",
            "publishedAt": "2023-04-01T12:35:46.000Z"
          }
        },
        {
          "kind": "youtube#comment",
          "id": "COMMENT_ID_2",
          "snippet": {
            "text": "This is another sample comment.",
            "publishedAt": "2023-04-01T12:36:36.000Z"
          }
        }
      ]
    },
    // More video items...
  ]
}
```

#### Note:
Make sure to replace `YOUR_E_TAG` and `VIDEO_ID_1`, `COMMENT_ID_1`, and `COMMENT_ID_2` with actual values obtained from the API.

### **Step 2: Analyze Most Popular Reviews and Comments**

#### Command:
```bash
run_command "grep -E '(review|comment) (content|body)' sessions/2026-05-15T07-35/youtube.md | sort -n | uniq -c"
```

**Expected Output:**
```
  4   Review content
  2   Comment body
  1   Review title
  1   Comment text
```

#### Note:
This command will list the most popular reviews and comments based on their occurrence.

### **Step 3: Generate Hash Tags**

#### Command:
```bash
run_command "echo 'Popular Hash Tags: review, comment, content, body' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Popular Hash Tags: review,#comment,#content,#body
```

### **Step 4: Adjust Posting Time**

#### Command:
```bash
run_command "echo 'Adjust Posting Time: 2023-05-18T00:00:00.000Z' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Adjust Posting Time: #2023-05-18T00:00:00.000Z
```

### **Step 5: Update Hash Tags and Posting Time in YouTube API**

#### Command:
```bash
run_command "python -m api.update_video_hashtags_and_posting_time $VIDEO_ID_1 --hashtags '$Popular Hash Tags' --posting-time '$Adjust Posting Time'"
```

**Expected Output:**
```
Video updated successfully with hashtags and posting time.
```

### **Step 6: Send Notification to Users**

#### Command:
```bash
run_command "echo 'Notification Sent: Review & Comment Analysis & Hash Tag & Posting Time Adjustment' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Notification Sent: #Review,#Comment,#Analysis,#HashTag,#PostingTimeAdjustment
```

### **Step 7: Check Results**

#### Command:
```bash
run_command "python -m api.check_video_hashtags_and_posting_time $VIDEO_ID_1"
```

**Expected Output:**
```
Video has updated hashtags and posting time.
```

### **Conclusion**

By analyzing recent reviews and comments, identifying the most popular topics, generating hash tags, and adjusting posting times in the YouTube API, we can increase the visibility of the channel. This approach ensures that the most relevant content is prominently featured and generates maximum engagement.

```yaml
---
title: "Review & Comment Analysis & Hash Tag & Posting Time Adjustment"
description: "Analyze and adjust hashtags and posting time for the most popular reviews and comments."
---

### **Step 1: Retrieve Recent Reviews and Comments**

#### Command:
```bash
run_command "youtube search --channel $YOUTUBE_CHANNEL_ID --max-results 10 --order date --part snippet,comments"
```

**Expected Output:**
```
{
  "kind": "youtube#searchListResponse",
  "etag": "\"YOUR_E_TAG\"",
  "pageInfo": {
    "totalResults": 10,
    "resultsPerPage": 10
  },
  "items": [
    {
      "kind": "youtube#video",
      "id": "VIDEO_ID_1",
      "snippet": {
        "title": "Review 1",
        "description": "This is a sample review.",
        "publishedAt": "2023-04-01T12:34:56.000Z"
      },
      "comments": [
        {
          "kind": "youtube#comment",
          "id": "COMMENT_ID_1",
          "snippet": {
            "text": "This is a sample comment.",
            "publishedAt": "2023-04-01T12:35:46.000Z"
          }
        },
        {
          "kind": "youtube#comment",
          "id": "COMMENT_ID_2",
          "snippet": {
            "text": "This is another sample comment.",
            "publishedAt": "2023-04-01T12:36:36.000Z"
          }
        }
      ]
    },
    // More video items...
  ]
}
```

#### Note:
Make sure to replace `YOUR_E_TAG` and `VIDEO_ID_1`, `COMMENT_ID_1`, and `COMMENT_ID_2` with actual values obtained from the API.

### **Step 2: Analyze Most Popular Reviews and Comments**

#### Command:
```bash
run_command "grep -E '(review|comment) (content|body)' sessions/2026-05-15T07-35/youtube.md | sort -n | uniq -c"
```

**Expected Output:**
```
  4   Review content
  2   Comment body
  1   Review title
  1   Comment text
```

#### Note:
This command will list the most popular reviews and comments based on their occurrence.

### **Step 3: Generate Hash Tags**

#### Command:
```bash
run_command "echo 'Popular Hash Tags: review, comment, content, body' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Popular Hash Tags: review,#comment,#content,#body
```

### **Step 4: Adjust Posting Time**

#### Command:
```bash
run_command "echo 'Adjust Posting Time: 2023-05-18T00:00:00.000Z' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Adjust Posting Time: #2023-05-18T00:00:00.000Z
```

### **Step 5: Update Hash Tags and Posting Time in YouTube API**

#### Command:
```bash
run_command "python -m api.update_video_hashtags_and_posting_time $VIDEO_ID_1 --hashtags '$Popular Hash Tags' --posting-time '$Adjust Posting Time'"
```

**Expected Output:**
```
Video updated successfully with hashtags and posting time.
```

### **Step 6: Send Notification to Users**

#### Command:
```bash
run_command "echo 'Notification Sent: Review & Comment Analysis & Hash Tag & Posting Time Adjustment' | sed -e 's/ /#/'"
```

**Expected Output:**
```
Notification Sent: #Review,#Comment,#Analysis,#HashTag,#PostingTimeAdjustment
```

### **Step 7: Check Results**

#### Command:
```bash
run_command "python -m api.check_video_hashtags_and_posting_time $VIDEO_ID_1"
```

**Expected Output:**
```
Video has updated hashtags and posting time.
```

### **Conclusion**

By analyzing recent reviews and comments, identifying the most popular topics, generating hash tags, and adjusting posting times in the YouTube API, we can increase the visibility of the channel. This approach ensures that the most relevant content is prominently featured and generates maximum engagement.
