Traceback (most recent call last):
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/engine/trainer.py"
, line 714, in get_dataset
    data = check_det_dataset(self.args.data)
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/data/utils.py"
, line 531, in check_det_dataset
    raise FileNotFoundError(m)
FileNotFoundError: Dataset '/home/malvm/projects/marimo/dataset/passport_down/data.yaml' images not found, missing path '/home/malvm/projects/marimo/images/val'
Note dataset download directory is '/home/malvm/projects/marimo/datasets'. You can update this in '/root/.config/Ultralytics/settings.json'

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/marimo/_runtime/executor.py"
, line 139, in execute_cell
    return eval(cell.last_expr, glbls)
  Cell 
marimo:///home/malvm/projects/marimo/model_train.py#cell=cell-2
, line 
1, in <module>
    model.train(
    ~~~~~~~~~~~^
        data="/home/malvm/projects/marimo/dataset/passport_down/data.yaml",
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    ...<8 lines>...
        verbose=True,
        ^^^^^^^^^^^^^
    )
    ^
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/engine/model.py"
, line 783, in train
    self.trainer = (trainer or self._smart_load("trainer"))(overrides=args, _callbacks=self.callbacks)
                   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/models/yolo/obb/train.py"
, line 47, in __init__
    super().__init__(cfg, overrides, _callbacks)
    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/models/yolo/detect/train.py"
, line 63, in __init__
    super().__init__(cfg, overrides, _callbacks)
    ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/engine/trainer.py"
, line 186, in __init__
    self.data = self.get_dataset()
                ~~~~~~~~~~~~~~~~^^
  File "/root/.cache/uv/archive-v0/d_qOYoSyOXWXa6w6/lib/python3.14/site-packages/ultralytics/engine/trainer.py"
, line 718, in get_dataset
    raise RuntimeError(emojis(f"Dataset '{clean_url(self.args.data)}' error ❌ {e}")) from e
RuntimeError: Dataset '/home/malvm/projects/marimo/dataset/passport_down/data.yaml' error ❌ Dataset '/home/malvm/projects/marimo/dataset/passport_down/data.yaml' images not found, missing path '/home/malvm/projects/marimo/images/val'
Note dataset download directory is '/home/malvm/projects/marimo/datasets'. You can update this in '/root/.config/Ultralytics/settings.json'
