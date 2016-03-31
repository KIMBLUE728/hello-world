# hello-world
just a test


- (void)openCamera {
    
    ZLCameraViewController *cameraVc = [[ZLCameraViewController alloc] init];
    cameraVc.maxCount = 10 - self.uploadImages.count;
    __weak PublishImageCtr *tCtr = self;
    cameraVc.callback = ^(NSArray *cameras){
        // 将拍照图片添加到数组
        [tCtr.uploadImages addObjectsFromArray:cameras];
        tCtr.alreadyPhotoCount = tCtr.uploadImages.count;
        // 刷新图片视图
        [tCtr reloadPhotosView];
    };
    [cameraVc showPickerVc:self];
}
