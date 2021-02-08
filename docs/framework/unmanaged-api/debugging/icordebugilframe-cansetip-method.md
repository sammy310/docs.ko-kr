---
description: '자세히 알아보기: ICorDebugILFrame:: CanSetIP 메서드'
title: ICorDebugILFrame::CanSetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: d6ba0d073e8807ac6173f7f3e3982fe1d3eb4e01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791441"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="865ae-103">ICorDebugILFrame::CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="865ae-103">ICorDebugILFrame::CanSetIP Method</span></span>

<span data-ttu-id="865ae-104">MSIL (Microsoft 중간 언어) 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="865ae-104">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865ae-105">구문</span><span class="sxs-lookup"><span data-stu-id="865ae-105">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="865ae-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="865ae-106">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="865ae-107">진행 명령 포인터에 대 한 원하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="865ae-107">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="865ae-108">설명</span><span class="sxs-lookup"><span data-stu-id="865ae-108">Remarks</span></span>  

 <span data-ttu-id="865ae-109">`CanSetIP` [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) 메서드를 호출 하기 전에 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="865ae-109">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="865ae-110">가 `CanSetIP` S_OK 이외의 HRESULT를 반환 하는 경우에도를 호출할 수 `ICorDebugILFrame::SetIP` 있지만 디버거가 디버깅 중인 코드의 안전 하 고 올바른 실행을 계속 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="865ae-110">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="865ae-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="865ae-111">Requirements</span></span>  

 <span data-ttu-id="865ae-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865ae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="865ae-113">**헤더:** CorDebug .idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="865ae-113">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="865ae-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="865ae-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="865ae-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="865ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
