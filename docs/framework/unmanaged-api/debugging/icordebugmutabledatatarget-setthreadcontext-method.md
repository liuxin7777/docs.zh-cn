---
title: ICorDebugMutableDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6629af393eeadb68292f8f2360ecb60c09a0cd03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764610"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext 方法
设置某个线程的上下文（寄存器值）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>参数  
 `dwThreadID`  
 [in] 由操作系统定义的线程标识符。  
  
 `contextSize`  
 [in] 要写入的 `pContext` 缓冲区的大小。  
  
 `pContext`  
 [in] 指向要写入的字节的指针。  
  
## <a name="remarks"></a>备注  
 `SetThreadContext` 方法将更新由操作系统定义的 `dwThreadID` 参数指定的当前线程上下文。 上下文记录的格式由所指示的平台[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。 这是 Windows，[上下文](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context)结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMutableDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
