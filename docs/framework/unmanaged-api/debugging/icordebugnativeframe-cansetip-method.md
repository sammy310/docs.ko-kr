---
title: ICorDebugNativeFrame::CanSetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd16db8c009fe81f2674a8bf9c7ad3a2a4827777
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927350"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="747ab-102">ICorDebugNativeFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="747ab-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="747ab-103">네이티브 코드에서 지정된 된 오프셋된 위치에는 IP (명령 포인터)를 설정할 수 인지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="747ab-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="747ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="747ab-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="747ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="747ab-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="747ab-106">[in] 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="747ab-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="747ab-107">설명</span><span class="sxs-lookup"><span data-stu-id="747ab-107">Remarks</span></span>  
 <span data-ttu-id="747ab-108">사용 된 `CanSetIP` 메서드를 호출 하기 전에 [icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="747ab-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="747ab-109">하는 경우 `CanSetIP` HRESULT를 반환 S_OK 이외의 여전히를 호출할 수 있습니다 `ICorDebugNativeFrame::SetIP`, 이지만 디버거에서 디버깅 중인 코드가 안전 하 고 올바른 실행을 계속는 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="747ab-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="747ab-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="747ab-110">Requirements</span></span>  
 <span data-ttu-id="747ab-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="747ab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="747ab-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="747ab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="747ab-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="747ab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="747ab-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="747ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="747ab-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="747ab-115">See also</span></span>
