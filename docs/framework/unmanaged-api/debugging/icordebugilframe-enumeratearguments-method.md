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
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703228"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="0e015-102">ICorDebugILFrame::EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="0e015-102">ICorDebugILFrame::EnumerateArguments Method</span></span>

<span data-ttu-id="0e015-103">이 프레임의 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e015-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e015-104">구문</span><span class="sxs-lookup"><span data-stu-id="0e015-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e015-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e015-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="0e015-106">제한이 이 프레임의 인수에 대 한 열거자 인 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0e015-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e015-107">설명</span><span class="sxs-lookup"><span data-stu-id="0e015-107">Remarks</span></span>  

 <span data-ttu-id="0e015-108">`EnumerateArguments` 이 ICorDebugILFrame 개체가 나타내는 호출 프레임에서 사용할 수 있는 인수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0e015-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="0e015-109">이 목록에는 [vararg](/cpp/windows/vararg) (즉, 인수의 가변 수) 및이 아닌 인수에 해당 하는 인수가 포함 됩니다 `vararg` .</span><span class="sxs-lookup"><span data-stu-id="0e015-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e015-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e015-110">Requirements</span></span>  

 <span data-ttu-id="0e015-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e015-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e015-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e015-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e015-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e015-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e015-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e015-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
