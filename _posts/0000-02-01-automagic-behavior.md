# The problem

How many times have you seen an API like this?

```python
def read_file(path_or_buffer: Union[str, IO[str]], *args, **kwargs) -> OutClass:
    if isinstance(path_or_buffer, str):
        return read_from_str(path_or_buffer)
    else:
        return read_from_io(path_or_buffer)
```


<div class="fragment">
Or like this?

```python
def somefunc(return_extra: bool=False) -> Union[str, Tuple[str]]:
    rv = 'Foo'
    if return_extra:
        return rv, extra
    return rv
```


```pycon
>>> print(somefunc())
Foo
>>> print(somefunc(return_extra)
('Foo', 'extra')
```
</div>
