<h1 align="center">The Suniv DMA</h1>

TODO
------------------------------

- [x] device_prep_dma_memcpy

- [ ] make delicate dma work in liner mode

- [ ] device_prep_slave_sg

- [ ] device_prep_dma_memset

- [ ] device_prep_dma_memset_sg

- [ ] device_prep_dma_cyclic

Testing Normal DMA Channel
------------------------------
```shell
cd /sys/module/dmatest/parameters

# loop count
# when should tx_status get called
echo 100 > iterations
echo 1 > timeout

# add channel testing thread
echo 0 > channel

echo dma0chan0 > channel
echo dma0chan1 > channel
echo dma0chan2 > channel
echo dma0chan3 > channel
echo dma0chan4 > channel
echo dma0chan5 > channel
echo dma0chan6 > channel
echo dma0chan7 > channel

echo 1 > run

echo 0 > run

```
> The Delicate DMA shouldn't test by this method, because it work in liner mode
> If address is not liner, the work process of delicate dma will stop

- References :
    - [DMAEngine documentation](https://docs.kernel.org/driver-api/dmaengine/index.html)
    - [DMAengine controller documentation](https://docs.kernel.org/driver-api/dmaengine/provider.html)
    - [DMA Test Guide](https://docs.kernel.org/driver-api/dmaengine/dmatest.html)
