---
title: SRBEX\_DATA\_SCSI\_CDB32 structure
description: The SRBEX\_DATA\_SCSI\_CDB32 structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).
ms.assetid: 8BE53883-2FD0-4CAB-928E-532587DA80C3
keywords:
- SRBEX_DATA_SCSI_CDB32 structure Storage Devices
- PSRBEX_DATA_SCSI_CDB32 structure pointer Storage Devices
topic_type:
- apiref
api_name:
- SRBEX_DATA_SCSI_CDB32
api_location:
- Storport.h
api_type:
- HeaderDef
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: structure
ms.date: 05/31/2018
---

# SRBEX\_DATA\_SCSI\_CDB32 structure

The **SRBEX\_DATA\_SCSI\_CDB32** structure contains the extended SRB data for a 32-byte SCSI command data block (CDB).

> [!Note]  
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver) and [Storport miniport](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers) driver models.

 

## Syntax


```C++
typedef struct _SRBEX_DATA_SCSI_CDB32 {
  SRBEXDATATYPE       Type;
  ULONG               Length;
  UCHAR               ScsiStatus;
  UCHAR               SenseInfoBufferLength;
  ULONG               CdbLength;
  UCHAR               Reserved;
  ULONG               Reserved1;
  PVOID POINTER_ALIGN SenseInfoBuffer;
  UCHAR POINTER_ALIGN Cdb[32];
} SRBEX_DATA_SCSI_CDB32, *PSRBEX_DATA_SCSI_CDB32;
```



## Members

<dl> <dt>

**Type**
</dt> <dd>

Data type indicator for the bidirectional extended SRB data structure. Set to **SrbExDataTypeScsiCdb32**.

</dd> <dt>

**Length**
</dt> <dd>

Length of the data in this structure starting with the **ScsiStatus** member. Set to SRBEX\_DATA\_SCSI\_CDB32\_LENGTH.

</dd> <dt>

**ScsiStatus**
</dt> <dd>

The SCSI status code returned for the submitted SRB.

</dd> <dt>

**SenseInfoBufferLength**
</dt> <dd>

The length of the sense information returned in the buffer pointed to by **SenseInfoBuffer**.

</dd> <dt>

**CdbLength**
</dt> <dd>

The length of the CDB data, in bytes, of the **Cdb** array.

</dd> <dt>

**Reserved**
</dt> <dd>

This member is reserved. Set to 0.

</dd> <dt>

**Reserved1**
</dt> <dd>

This member is reserved. Set to 0.

</dd> <dt>

**SenseInfoBuffer**
</dt> <dd>

A pointer to a buffer containing any returned sense information.

</dd> <dt>

**Cdb**
</dt> <dd>

The 32-byte CDB buffer.

</dd> </dl>

## Remarks

This structure is used to submit an extended SRB data for a CDB of 32 bytes or less.

## Requirements



|                    |                                                                                                                                  |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Version<br/> | Available starting with Windows 8.<br/>                                                                                    |
| Header<br/>  | <dl> <dt>Storport.h (include Storport.h, Srb.h, or Minitape.h)</dt> </dl> |



## See also

<dl> <dt>

[**SRBEX\_DATA\_SCSI\_CDB16**](srbex-data-scsi-cdb16.md)
</dt> <dt>

[**STORAGE\_REQUEST\_BLOCK**](storage-request-block.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20SRBEX_DATA_SCSI_CDB32%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





