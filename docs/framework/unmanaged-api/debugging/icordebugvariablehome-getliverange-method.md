---
description: '자세히 알아보기: IcorDebugVariableHome:: GetLiveRange 메서드'
title: 'IcorDebugVariableHome:: GetLiveRange 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: daa53a164c7660826d44285ce21ecea1b649a727
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800840"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="7c326-103">IcorDebugVariableHome:: GetLiveRange 메서드</span><span class="sxs-lookup"><span data-stu-id="7c326-103">IcorDebugVariableHome::GetLiveRange Method</span></span>

<span data-ttu-id="7c326-104">이 변수가 활성 상태인 기본 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c326-104">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c326-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c326-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c326-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c326-106">Parameters</span></span>  

 `pStartOffset`  
 <span data-ttu-id="7c326-107">제한이 변수가 첫 번째 라이브 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="7c326-107">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="7c326-108">제한이 변수가 마지막으로 지속 된 지점 바로 다음의 논리적 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="7c326-108">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c326-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c326-109">Requirements</span></span>  

 <span data-ttu-id="7c326-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c326-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c326-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c326-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c326-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c326-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c326-113">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c326-113">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c326-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c326-114">See also</span></span>

- [<span data-ttu-id="7c326-115">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c326-115">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
