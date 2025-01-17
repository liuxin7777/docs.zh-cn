---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a878ccf94fb4f6d67daa3a4dd42fcf98faf34a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748637"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 从内存中的符号流读取字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>参数  
 `moduleId`  
 [in]包含内存中流的模块标识符。  
  
 `symbolsReadOffset`  
 [in]在开始读取字节的内存中流内的偏移量。  
  
 `pSymbolBytes`  
 [out]指向数据将复制到其中的缓冲区的指针。 缓冲区应具有`countSymbolBytes`的可用空间。  
  
 `countSymbolBytes`  
 [in]要复制的字节数。  
  
 `pCountSymbolBytesRead`  
 [out]方法返回时，包含实际读取的字节数。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果已读取的字节非零值数。  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`如果该模块使用创建<xref:System.Reflection.Emit>。  
  
## <a name="remarks"></a>备注  
 `ReadInMemorySymbols`方法会尝试读取`countSymbolBytes`的数据偏移量开始`symbolsReadOffset`中内存流中。 将数据复制到`pSymbolBytes`，这都必须具有`countSymbolBytes`的可用空间。     `pCountSymbolsBytesRead` 包含实际读取，这可能会更少的字节数比`countSymbolBytes`如果到达流的末尾。  
  
> [!NOTE]
>  当前实现不支持 Reflection.Emit。 如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
