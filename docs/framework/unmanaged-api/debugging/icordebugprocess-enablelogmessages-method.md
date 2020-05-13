---
title: ICorDebugProcess::EnableLogMessages 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: 3b850a462ce354b81f4406fce7fd9d8d9b6013d8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207898"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="ecd39-102">ICorDebugProcess::EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="ecd39-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="ecd39-103">디버거로 로그 메시지 전송을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecd39-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd39-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecd39-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecd39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecd39-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="ecd39-106">[in] `true` 로그 메시지를 전송할 수 있도록 합니다. `false`전송을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecd39-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecd39-107">설명</span><span class="sxs-lookup"><span data-stu-id="ecd39-107">Remarks</span></span>  
 <span data-ttu-id="ecd39-108">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백이 발생 한 후에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecd39-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecd39-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecd39-109">Requirements</span></span>  
 <span data-ttu-id="ecd39-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecd39-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecd39-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecd39-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecd39-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecd39-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecd39-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecd39-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
