# Shelfnet18 Realtime Logger

[_Documentation generated by Documatic_](https://www.documatic.com)

<!---Documatic-section-Codebase Structure-start--->
## Codebase Structure

<!---Documatic-block-system_architecture-start--->
```mermaid
None
```
<!---Documatic-block-system_architecture-end--->

# #
<!---Documatic-section-Codebase Structure-end--->

<!---Documatic-section-ShelfNet18_realtime.logger.setup_logger-start--->
## ShelfNet18_realtime.logger.setup_logger

<!---Documatic-section-setup_logger-start--->
<!---Documatic-block-ShelfNet18_realtime.logger.setup_logger-start--->
<details>
	<summary><code>ShelfNet18_realtime.logger.setup_logger</code> code snippet</summary>

```python
def setup_logger(logpth):
    logfile = 'BiSeNet-{}.log'.format(time.strftime('%Y-%m-%d-%H-%M-%S'))
    logfile = osp.join(logpth, logfile)
    FORMAT = '%(levelname)s %(filename)s(%(lineno)d): %(message)s'
    log_level = logging.INFO
    if dist.is_initialized() and (not dist.get_rank() == 0):
        log_level = logging.ERROR
    logging.basicConfig(level=log_level, format=FORMAT, filename=logfile)
    logging.root.addHandler(logging.StreamHandler())
```
</details>
<!---Documatic-block-ShelfNet18_realtime.logger.setup_logger-end--->
<!---Documatic-section-setup_logger-end--->

# #
<!---Documatic-section-ShelfNet18_realtime.logger.setup_logger-end--->

[_Documentation generated by Documatic_](https://www.documatic.com)