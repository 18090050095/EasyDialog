# EasyDialog
�ṩ�Զ���dialog style�Ŀ⣬���Զ���view������ԭ��!   

### ���  
ԭ���ṩ��dialog��������Ƹ����ı�׼������һ���������ȥͨ���Զ���viewȻ������dialog���������������ַ�ʽ�е���ˣ���ʵ����ֻ��Ҫͨ��style�ļ����滻dialogĬ�ϵĲ���Ϊ�����Զ���Ĳ��־Ϳ����ˡ������ķ�ʽ�Ȳ��øı�dialog��ʹ�÷�ʽ��Ҳ����д������룬ֻ��Ҫ������ʽ����������������ʵҲ��android�����˼�룬�ٷ�һ�㶼�������ֵ��¶������������SDK��ʱ��ҲӦ����ѭ���ֱ�׼������ʾ���߼��ֿ�����ʾ�������ֿ��Խ���style���塣

### �������
1.���JitPack�ֿ�
  
```  
repositories {
	maven {
		url "https://jitpack.io"
	}
}
```   
```  
dependencies {
		compile 'com.github.tianzhijiexian:��û����'
}    
```   
### ʹ�÷�ʽ   
**������������Ĭ����ʽ��һ�����þ͸㶨��**  
```XML  
<resources>

    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        
        <item name="dialogTheme">@style/Theme.Dialog</item>
        <item name="alertDialogTheme">@style/Theme.AppCompat.Light.Dialog.Alert</item>
        <item name="alertDialogStyle">@style/AlertDialog</item>
        <item name="progressDialogStyle">@style/ProgressDialog</item>

        <item name="dialogPreferredPadding">@dimen/abc_dialog_padding_material</item>
        <item name="alertDialogCenterButtons">false</item>
        <item name="textColorAlertDialogListItem">@color/abc_primary_text_material_light</item>
        <!-- dialog��listView��divider -->
        <item name="listDividerAlertDialog">@null</item>
        
    </style>

</resources>  
```  
������ô�򵥣�һ�ж��㶨�ˣ�   
�����ڴ�����ֱ���öԻ���Ϳ����ˣ��Ի����ʹ�÷�ʽ��֮ǰû���κ�����  
```JAVA  
AlertDialog dialog = new AlertDialog.Builder(this)
                //.setIconAttribute(android.R.attr.alertDialogIcon)
                .setTitle("title")
                //.setMessage("message") // ������б�Ͳ�Ҫ����message�ˣ�����������
                .setPositiveButton("��", null)
                .setNeutralButton("��", null)
                .setNegativeButton("��", null)
                .setItems(new String[]{"android","ios","wp"}, new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                    }
                }).create();

        dialog.show();
        dialog.setOnDismissListener(new DialogInterface.OnDismissListener() {
            @Override
            public void onDismiss(DialogInterface dialog) {
                Toast.makeText(MainActivity.this, "dimiss", Toast.LENGTH_SHORT).show();
                dialog.dismiss();
            }
        });


        // ProgressDialog.show(this, "title", "test message");  
```   

### ����  
���ǲ���ԭ������ʽ�϶������������ǵ����������ھ�������������Լ���style�ɡ�  
```XML   
<resources>

    <style name="Theme.Dialog" parent="Theme.AppCompat.Light.Dialog">
        <item name="android:colorBackground">@color/background_floating_material_light</item>
        <item name="android:colorBackgroundCacheHint">@null</item>

        <item name="android:windowFrame">@null</item>
        <item name="android:windowTitleStyle">@style/RtlOverlay.DialogWindowTitle.AppCompat</item>
        <item name="android:windowTitleBackgroundStyle">@style/Base.DialogWindowTitleBackground.AppCompat</item>
        <item name="android:windowBackground">@drawable/abc_dialog_material_background_light</item>
        <item name="android:windowIsFloating">true</item>
        <item name="android:backgroundDimEnabled">true</item>
        <item name="android:windowContentOverlay">@null</item>
        <item name="android:windowAnimationStyle">@style/Animation.AppCompat.Dialog</item>
        <item name="android:windowSoftInputMode">stateUnspecified|adjustPan</item>

        <item name="windowActionBar">false</item>
        <item name="windowActionModeOverlay">true</item>

        <item name="listPreferredItemPaddingLeft">24dip</item>
        <item name="listPreferredItemPaddingRight">24dip</item>

        <item name="android:listDivider">@null</item>

        <item name="windowMinWidthMajor">@dimen/abc_dialog_min_width_major</item>
        <item name="windowMinWidthMinor">@dimen/abc_dialog_min_width_minor</item>
    </style>

    <style name="AlertDialog" parent="Base.AlertDialog.AppCompat">
        <!-- AlertController.class - line:168 -->
        <!-- dialog�����岼���ļ������������title��message�ȿؼ� -->
        <item name="android:layout">@layout/custom_dialog_alert_material</item>
        <!-- dialog�е��б����ļ�����ʵ����listview -->
        <item name="listLayout">@layout/custom_dialog_list_material</item>
        <!-- dialog���б��item�Ĳ��� -->
        <item name="listItemLayout">@layout/custom_dialog_select_item_material</item>
        <!-- ��ѡ��item�Ĳ��� -->
        <item name="multiChoiceItemLayout">@layout/custom_dialog_select_multichoice_material</item>
        <!-- ��ѡ��item�Ĳ��� -->
        <item name="singleChoiceItemLayout">@layout/custom_dialog_select_singlechoice_material</item>
    </style>

    <style name="ProgressDialog">
        <!-- ����Ľ��������� -->
        <item name="horizontalProgressLayout">@layout/custom_dialog_progress_horizontal_material</item>
        <!-- Բ�ν��������� -->
        <item name="progressLayout">@layout/custom_dialog_progress</item>
    </style>

</resources>

```   
ֻҪ����������ݸ��Ƶ��Լ���Ŀ��style�У�Ȼ��ȥ�ο�����layout�ļ�������滻�Լ���layout�ļ����С���ȫ����è������û���κμ����Ѷȣ�



### ������
![](https://avatars3.githubusercontent.com/u/9552155?v=3&s=460)

Jack Tony: <developer_kale@.com>  


### License

    Copyright 2015 Jack Tony

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
 