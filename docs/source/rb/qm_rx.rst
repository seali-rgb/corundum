.. _rb_qm_rx:

=====================================
Receive queue manager register block
=====================================

The receive queue manager register block has a header with type 0x0000C021, version 0x00000200, and indicates the location of the receive queue manager registers and number of queues.

.. table::

    ========  =============  ======  ======  ======  ======  =============
    Address   Field          31..24  23..16  15..8   7..0    Reset value
    ========  =============  ======  ======  ======  ======  =============
    RBB+0x00  Type           Vendor ID       Type            RO 0x0000C021
    --------  -------------  --------------  --------------  -------------
    RBB+0x04  Version        Major   Minor   Patch   Meta    RO 0x00000200
    --------  -------------  ------  ------  ------  ------  -------------
    RBB+0x08  Next pointer   Pointer to next register block  RO -
    --------  -------------  ------------------------------  -------------
    RBB+0x0C  Offset         Offset to queue manager         RO -
    --------  -------------  ------------------------------  -------------
    RBB+0x10  Count          Queue count                     RO -
    --------  -------------  ------------------------------  -------------
    RBB+0x14  Stride         Queue control register stride   RO 0x00000020
    ========  =============  ==============================  =============

See :ref:`rb_overview` for definitions of the standard register block header fields.

.. object:: Offset

    The offset field contains the offset to the start of the receive queue manager region, relative to the start of the current region.

    .. table::

        ========  ======  ======  ======  ======  =============
        Address   31..24  23..16  15..8   7..0    Reset value
        ========  ======  ======  ======  ======  =============
        RBB+0x0C  Offset to queue manager         RO -
        ========  ==============================  =============

.. object:: Count

    The count field contains the number of queues.

    .. table::

        ========  ======  ======  ======  ======  =============
        Address   31..24  23..16  15..8   7..0    Reset value
        ========  ======  ======  ======  ======  =============
        RBB+0x10  Queue count                     RO -
        ========  ==============================  =============

.. object:: Stride

    The stride field contains the size of the control registers associated with each queue.

    .. table::

        ========  ======  ======  ======  ======  =============
        Address   31..24  23..16  15..8   7..0    Reset value
        ========  ======  ======  ======  ======  =============
        RBB+0x14  Queue control register stride   RO 0x00000020
        ========  ==============================  =============

Queue manager CSRs
==================

Each queue has several associated control registers, detailed in this table:

.. table::

    =========  ==============  ======  ======  ======  ======  =============
    Address    Field           31..24  23..16  15..8   7..0    Reset value
    =========  ==============  ======  ======  ======  ======  =============
    Base+0x00  Base address L  Ring base address (lower 32)    RW -
    ---------  --------------  ------------------------------  -------------
    Base+0x04  Base address H  Ring base address (upper 32)    RW -
    ---------  --------------  ------------------------------  -------------
    Base+0x08  Control 1       Active                  Size    RW -
    ---------  --------------  ------  ------  ------  ------  -------------
    Base+0x0C  Control 2                       CQ index        RW -
    ---------  --------------  --------------  --------------  -------------
    Base+0x10  Head pointer                    Head pointer    RW -
    ---------  --------------  --------------  --------------  -------------
    Base+0x18  Tail pointer                    Tail pointer    RW -
    =========  ==============  ==============  ==============  =============
