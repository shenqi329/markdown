## Why Binder
Linux传统的通信方式中能够完成RPC的有管道、socket等手段


```
for (; offset < offsets_size; offset++) {
	....
	hdr = (struct binder_object_header *)(t->buffer->data + offset);
	
	switch (hdr->type) {
		case BINDER_TYPE_BINDER:
		case BINDER_TYPE_WEAK_BINDER: {
			struct flat_binder_object *fp;
			fp = to_flat_binder_object(hdr);
			struct flat_binder_object *fp;
			binder_translate_binder(fp, t, thread);//转换binder
		} break;
		case BINDER_TYPE_HANDLE:
		case BINDER_TYPE_WEAK_HANDLE: {
			struct flat_binder_object *fp;
			fp = to_flat_binder_object(hdr);
			ret = binder_translate_handle(fp, t, thread);//转换handle
		} break;
		case BINDER_TYPE_FD: {
			struct flat_binder_object *fp;
			fp = to_flat_binder_object(hdr);
			binder_translate_fd(fp->fd, t, thread, in_reply_to);//转换文件句柄
		} break;
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbODMxMDE4OTQzLDk5MjAwMTg4NV19
-->