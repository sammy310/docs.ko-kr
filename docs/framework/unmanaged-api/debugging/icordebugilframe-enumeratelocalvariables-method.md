---
description: '자세히 알아보기: ICorDebugILFrame:: EnumerateLocalVariables 메서드'
title: ICorDebugILFrame::EnumerateLocalVariables 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 275cf7fcad32c452e6e7ebdd0774d64708a2398c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791389"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="65a86-103">ICorDebugILFrame::EnumerateLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="65a86-103">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>

<span data-ttu-id="65a86-104">이 프레임의 지역 변수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65a86-104">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a86-105">구문</span><span class="sxs-lookup"><span data-stu-id="65a86-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65a86-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65a86-106">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="65a86-107">[out] 이 프레임에서 로컬 변수의 열거자인 ICorDebugValueEnum 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="65a86-107">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65a86-108">설명</span><span class="sxs-lookup"><span data-stu-id="65a86-108">Remarks</span></span>  

 <span data-ttu-id="65a86-109">`EnumerateLocalVariables` 이 ICorDebugILFrame 개체가 나타내는 호출 프레임에서 사용할 수 있는 지역 변수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65a86-109">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="65a86-110">일부 지역 변수가 활성 상태가 아닐 수 있으므로이 목록에는 실행 중인 함수의 모든 지역 변수가 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a86-110">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a86-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65a86-111">Requirements</span></span>  

 <span data-ttu-id="65a86-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65a86-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a86-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65a86-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65a86-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65a86-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65a86-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
