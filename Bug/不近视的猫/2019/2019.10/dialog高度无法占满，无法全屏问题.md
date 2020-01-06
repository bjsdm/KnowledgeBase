# dialog高度无法占满，无法全屏问题

在初始化 dialog 后，加入以下代码

```
        Window dialogWindow = dialog.getWindow();
        WindowManager.LayoutParams lp = dialogWindow.getAttributes();
        lp.width = ViewGroup.LayoutParams.MATCH_PARENT;
        lp.height = ViewGroup.LayoutParams.MATCH_PARENT; //注意一定要是MATCH_PARENT
        dialogWindow.setAttributes(lp);
```

例如：

```
    @Override
    public void initDialogView(View view) {
        view.findViewById(R.id.tv_mobile_photo).setOnClickListener(this);
        view.findViewById(R.id.tv_shoot).setOnClickListener(this);
        view.findViewById(R.id.tv_cancel).setOnClickListener(this);
        view.findViewById(R.id.view_bg).setOnClickListener(this);

        Window dialogWindow = dialog.getWindow();
        WindowManager.LayoutParams lp = dialogWindow.getAttributes();
        lp.width = ViewGroup.LayoutParams.MATCH_PARENT;
        lp.height = ViewGroup.LayoutParams.MATCH_PARENT; //注意一定要是MATCH_PARENT
        dialogWindow.setAttributes(lp);
    }

```