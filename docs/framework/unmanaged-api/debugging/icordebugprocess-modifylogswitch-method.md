---
title: ICorDebugProcess::ModifyLogSwitch 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 3ac1b3606131f534195df9b6b59bf72b1bff27fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724535"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="df61d-102">ICorDebugProcess::ModifyLogSwitch 메서드</span><span class="sxs-lookup"><span data-stu-id="df61d-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>

<span data-ttu-id="df61d-103">지정 된 로그 스위치의 심각도 수준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df61d-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df61d-104">구문</span><span class="sxs-lookup"><span data-stu-id="df61d-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df61d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df61d-105">Parameters</span></span>  

 `pLogSwitchName`  
 <span data-ttu-id="df61d-106">진행 로그 스위치의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="df61d-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="df61d-107">진행 지정 된 로그 스위치에 대해 설정할 심각도 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="df61d-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df61d-108">설명</span><span class="sxs-lookup"><span data-stu-id="df61d-108">Remarks</span></span>  

 <span data-ttu-id="df61d-109">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백이 발생 한 후에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="df61d-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df61d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df61d-110">Requirements</span></span>  

 <span data-ttu-id="df61d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df61d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df61d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df61d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df61d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df61d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df61d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df61d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
