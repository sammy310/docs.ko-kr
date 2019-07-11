---
title: ICorDebugILFrame::GetLocalVariable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29fc1b491aa4e340c3d8ad6f761d0d6d901649ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758555"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="27bfa-102">ICorDebugILFrame::GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="27bfa-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="27bfa-103">이 Microsoft 중간 언어 (MSIL) 스택 프레임에서 지정 된 로컬 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27bfa-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27bfa-104">구문</span><span class="sxs-lookup"><span data-stu-id="27bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27bfa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27bfa-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="27bfa-106">[in] 이 MSIL 스택 프레임의 로컬 변수 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27bfa-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="27bfa-107">[out] 검색된 된 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27bfa-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27bfa-108">설명</span><span class="sxs-lookup"><span data-stu-id="27bfa-108">Remarks</span></span>  
 <span data-ttu-id="27bfa-109">`GetLocalVariable` 메서드는 MSIL 스택 프레임 또는 컴파일된 시간 (JIT)에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27bfa-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27bfa-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27bfa-110">Requirements</span></span>  
 <span data-ttu-id="27bfa-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27bfa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27bfa-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27bfa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27bfa-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27bfa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27bfa-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27bfa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
