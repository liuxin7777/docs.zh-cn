---
title: ICLRDataTarget::GetImageBase 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dbb655d6ed0b9bd88c5eedf61a191401a805fb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738752"
---
# <a name="iclrdatatargetgetimagebase-method"></a>ICLRDataTarget::GetImageBase 方法
获取指定的图像的基础内存地址。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>参数  
 `imagePath`  
 [in]映像，包括其路径的文件名。  
  
 `baseAddress`  
 [out]指向将存储映像的基址 CLRDATA_ADDRESS 的指针。  
  
## <a name="remarks"></a>备注  
 图像文件名称可能或可能不具有路径。 如果指定了路径，则整个路径; 上执行匹配否则，匹配仅上完成的文件的名称。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl, ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
