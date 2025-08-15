# Image Upload System Setup

## 🎯 **What This Does**

Instead of storing blurry compressed images in the database, this system:
- ✅ **Saves original quality images** as files on server
- ✅ **Stores only file paths** in database (e.g., "uploads/products/product_123.jpg")
- ✅ **No compression** = crystal clear images
- ✅ **Fast loading** = small database, optimized file serving

## 🔧 **Setup Instructions**

### **Step 1: Web Server Required**
You need a web server that supports PHP (like XAMPP, WAMP, or live hosting).

**For Local Development:**
1. Install XAMPP/WAMP
2. Place your project in `htdocs` folder
3. Start Apache server
4. Access via `http://localhost/your-project`

### **Step 2: Directory Permissions**
Make sure the uploads directory is writable:
```bash
chmod 755 uploads/
chmod 755 uploads/products/
```

### **Step 3: Database Update**
Your database is already compatible! The `image_url` column will now store:
- **Before**: `data:image/jpeg;base64,/9j/4AAQSkZJRg...` (huge)
- **After**: `uploads/products/product_123456.jpg` (small)

### **Step 4: Test Upload**
1. Open admin interface
2. Try uploading a product image
3. You should see "Uploading image..." then the full-quality preview

## 📁 **File Structure**
```
your-project/
├── stock.html (admin interface)
├── upload_image.php (handles file uploads)
└── uploads/
    └── products/
        ├── product_123456.jpg
        ├── product_789012.png
        └── ...
```

## 🔒 **Security Features**
- ✅ File type validation (only images)
- ✅ File size limit (5MB)
- ✅ Unique filenames prevent conflicts
- ✅ Directory traversal protection

## 🚀 **Benefits**
- ✅ **Crystal clear images** (no compression)
- ✅ **Fast database** (only stores paths)
- ✅ **Easy backup** (just copy uploads folder)
- ✅ **Scalable** (can use CDN later)

## 🛠️ **If No PHP Available**
Alternative options:
1. **Use Supabase Storage** (built-in file storage)
2. **Use Cloudinary** (image hosting service)
3. **Use AWS S3** (cloud storage)

Let me know if you need help with any of these alternatives!