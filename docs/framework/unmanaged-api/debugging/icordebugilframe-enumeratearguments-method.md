---
title: ICorDebugILFrame::EnumerateArguments 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131036"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="16140-102">ICorDebugILFrame::EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="16140-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="16140-103">이 프레임의 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16140-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16140-104">구문</span><span class="sxs-lookup"><span data-stu-id="16140-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16140-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16140-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="16140-106">제한이 이 프레임의 인수에 대 한 열거자 인 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16140-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16140-107">주의</span><span class="sxs-lookup"><span data-stu-id="16140-107">Remarks</span></span>  
 <span data-ttu-id="16140-108">`EnumerateArguments`이 ICorDebugILFrame 개체가 나타내는 호출 프레임에서 사용할 수 있는 인수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16140-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="16140-109">이 목록에는 `vararg`되지 않은 인수 뿐만 아니라 [vararg](/cpp/windows/vararg) (인수 개수) 인 인수가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16140-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16140-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16140-110">Requirements</span></span>  
 <span data-ttu-id="16140-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16140-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16140-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16140-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16140-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16140-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16140-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16140-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
