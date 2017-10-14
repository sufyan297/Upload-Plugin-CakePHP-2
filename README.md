# Upload-Plugin-CakePHP-2
Upload Plugin for CakePHP 2
Credits goes to https://github.com/josegonzalez/cakephp-upload/ for making such beautiful plugin.

# changes made by me
- Remove white spaces from filename.


# How to install?
- copy 'Upload' directory and paste it in app/Plugin/ folder.
- Add CakePlugin::load('Upload'); in app/Config/bootstrap.php to load the Upload Plugin.
- Add Upload Config in your Model. Where you want to use.

- for eg: we have Model/Admin.php
- Paste below content there.
`    public $actsAs = array(
                'Upload.Upload' => array(
                        // Field in the table which will store the path of the image
                        'image_file' => array(
                        // Allowed mime types
                        'mimetypes'=> array('image/jpg','image/jpeg', 'image/png'),
                        // Use php for localhost or where imagick is not installed
                        'thumbnailMethod'=>"php",
                        // Allowed set of extensions
                        'extensions'=> array('jpg','png','JPG','PNG','jpeg','JPEG'),
                        'thumbnailSizes' => array(
                        'tm'  => '[80x80]',
                        'sm'  => '[200x200]',
                        'api' => '[300x240]',
                        'md'  => '[500x400]',
                        'big' => '[800x640]',
                        'hd'  => '[1000x800]'
                    ),
                    // Map the directory path to specified field in the table
                    'fields' => array(
                        'dir' => 'image_dir'
                )
            )
        )
    );
`