# 🖼️ Adding Team Member Photos to Your Website

## Overview
This guide explains how to add actual team member photos to replace the placeholder avatars (👤) on your About Us page.

## 📋 Steps to Add Photos

### Step 1: Prepare Your Photos
1. Collect team member photos (JPG or PNG format)
2. **Recommended size**: 400x500 pixels or similar ratio
3. **Recommended file size**: Less than 500KB each
4. **Naming**: Name them simply like `member1.jpg`, `member2.jpg`, etc.

### Step 2: Create Images Folder Structure
If not already done:
1. Go to: `assets/images/`
2. Create a subfolder called `team/`
3. Place all team member photos in `assets/images/team/`

### Step 3: Update HTML Code

Open `pages/about-us.html` and find this section:

```html
<div class="team-member">
    <div class="member-image">👤</div>
    <div class="member-info">
        <h3>John Doe</h3>
        <div class="member-role">Project Lead & Senior Researcher</div>
        <div class="member-email">john.doe@bustransport.edu</div>
    </div>
</div>
```

**Replace the placeholder** with an image. Change:

```html
<div class="member-image">👤</div>
```

To:

```html
<div class="member-image" style="background: url('../assets/images/team/john-doe.jpg') center/cover;"></div>
```

### Step 4: Update All Team Members

Do this for each team member. Example with 3 members:

```html
<!-- Team Member 1 -->
<div class="team-member">
    <div class="member-image" style="background: url('../assets/images/team/member1.jpg') center/cover;"></div>
    <div class="member-info">
        <h3>John Doe</h3>
        <div class="member-role">Project Lead</div>
        <div class="member-email">john.doe@bustransport.edu</div>
    </div>
</div>

<!-- Team Member 2 -->
<div class="team-member">
    <div class="member-image" style="background: url('../assets/images/team/member2.jpg') center/cover;"></div>
    <div class="member-info">
        <h3>Jane Smith</h3>
        <div class="member-role">Lead Developer</div>
        <div class="member-email">jane.smith@bustransport.edu</div>
    </div>
</div>

<!-- Team Member 3 -->
<div class="team-member">
    <div class="member-image" style="background: url('../assets/images/team/member3.jpg') center/cover;"></div>
    <div class="member-info">
        <h3>Michael Johnson</h3>
        <div class="member-role">Data Analyst</div>
        <div class="member-email">michael.johnson@bustransport.edu</div>
    </div>
</div>
```

## 📸 Alternative: Using img Tag

If you prefer using the `<img>` tag instead:

```html
<div class="member-image">
    <img src="../assets/images/team/john-doe.jpg" alt="John Doe">
</div>
```

Then add this CSS to `assets/css/style.css`:

```css
.member-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}
```

## 🖼️ Image Size Recommendations

| Purpose | Width | Height | Size |
|---------|-------|--------|------|
| Team photo | 400px | 500px | < 500KB |
| Logo | 200px | 200px | < 100KB |
| Hero image | 1200px | 400px | < 1MB |
| Thumbnail | 300px | 200px | < 300KB |

## 🎨 Image Format Guidelines

**Best formats:**
- **JPG**: Good for photos, smaller file size
- **PNG**: Good for logos, supports transparency
- **WebP**: Modern format, even smaller (browser support may vary)

**Compression tools:**
- TinyPNG.com (free, simple)
- ImageOptim (macOS)
- FileZilla (has built-in compression)

## 📁 Final Folder Structure

After adding images, your structure should look like:

```
bustransport/
└── assets/
    ├── css/
    │   └── style.css
    └── images/
        └── team/
            ├── member1.jpg
            ├── member2.jpg
            ├── member3.jpg
            ├── member4.jpg
            ├── member5.jpg
            ├── member6.jpg
            ├── member7.jpg
            └── member8.jpg
```

## ✅ Verification Checklist

- [ ] All photos are in `assets/images/team/` folder
- [ ] Photo filenames match the HTML code
- [ ] Photos are optimized (< 500KB each)
- [ ] Paths in HTML start with `../assets/images/team/`
- [ ] All 8 team members have photos
- [ ] Photos display correctly when you open the website

## 🔧 Troubleshooting Photos

### Photos not showing?

1. **Check file path**: Is the path correct in the HTML?
   - From pages folder: `../assets/images/team/filename.jpg`
   - Check spelling and capitalization (case-sensitive on some servers)

2. **Check image files**: Do they exist in the folder?
   - Open your file explorer
   - Navigate to `assets/images/team/`
   - Make sure files are there

3. **Try absolute path temporarily**: For testing, use:
   ```html
   <div class="member-image" style="background: url('C:/Users/irang/OneDrive/Desktop/New folder (2)/bustransport/assets/images/team/member1.jpg') center/cover;"></div>
   ```
   If this works, the issue is relative path problem.

4. **Check browser console**: Press F12 and check for errors

### Photos look stretched or distorted?

The CSS includes `center/cover` which should maintain aspect ratio. If needed, adjust the height in CSS:

```css
.member-image {
    height: 250px; /* Adjust this value */
}
```

### Photos not fully visible?

If photos are cropped, try using `contain` instead of `cover`:

```html
<div class="member-image" style="background: url('../assets/images/team/member1.jpg') center/contain;"></div>
```

## 💡 Pro Tips

1. **Consistent Style**: Use photos with similar:
   - Lighting
   - Background
   - Positioning (face/upper body visible)
   - Aspect ratio

2. **Professional Look**: Consider:
   - Headshots or upper body photos
   - Professional attire
   - Good lighting
   - Simple/neutral background

3. **Backup**: Keep original photo files safe
   - Store originals in a backup folder
   - Version your edits

4. **Mobile Testing**: Test photos on mobile devices
   - Ensure they load properly
   - Check that they display well on small screens

## 🚀 Next Steps

1. Prepare your team member photos
2. Create the `assets/images/team/` folder
3. Place photos in the folder
4. Update the HTML code with image paths
5. Open `pages/about-us.html` in your browser to verify
6. Make any adjustments needed

---

**Need help?** Check that your image filenames don't have spaces. Replace spaces with hyphens (e.g., `john-doe.jpg` not `john doe.jpg`)
