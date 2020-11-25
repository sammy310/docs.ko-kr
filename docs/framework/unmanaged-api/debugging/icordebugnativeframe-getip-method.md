---
title: ICorDebugNativeFrame::GetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: c9c0598f8e7b3e8654124f50663c912f3cd61659
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709307"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="dffd7-102">ICorDebugNativeFrame::GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="dffd7-102">ICorDebugNativeFrame::GetIP Method</span></span>

<span data-ttu-id="dffd7-103">명령 포인터가 현재 설정 된 네이티브 코드 오프셋 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dffd7-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dffd7-104">구문</span><span class="sxs-lookup"><span data-stu-id="dffd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dffd7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dffd7-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="dffd7-106">제한이 네이티브 코드의 오프셋 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dffd7-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dffd7-107">설명</span><span class="sxs-lookup"><span data-stu-id="dffd7-107">Remarks</span></span>  

 <span data-ttu-id="dffd7-108">이 "ICorDebugNativeFrame"로 표시 되는 스택 프레임이 활성화 된 경우 오프셋은 실행할 다음 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dffd7-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="dffd7-109">이 스택 프레임이 활성화 되어 있지 않으면 오프셋은 스택 프레임을 다시 활성화할 때 실행 되는 다음 명령의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dffd7-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dffd7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dffd7-110">Requirements</span></span>  

 <span data-ttu-id="dffd7-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dffd7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dffd7-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dffd7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dffd7-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dffd7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dffd7-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dffd7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffd7-115">참조</span><span class="sxs-lookup"><span data-stu-id="dffd7-115">See also</span></span>
