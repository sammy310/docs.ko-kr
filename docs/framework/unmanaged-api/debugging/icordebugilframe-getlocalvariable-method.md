---
description: '자세히 알아보기: ICorDebugILFrame:: GetLocalVariable 메서드'
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
ms.openlocfilehash: c4bb3e5a5d970539607efbaf55f3f7f08f7e72af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791376"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="cd582-103">ICorDebugILFrame::GetLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="cd582-103">ICorDebugILFrame::GetLocalVariable Method</span></span>

<span data-ttu-id="cd582-104">이 MSIL (Microsoft 중간 언어) 스택 프레임에서 지정 된 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd582-104">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd582-105">구문</span><span class="sxs-lookup"><span data-stu-id="cd582-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd582-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd582-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="cd582-107">진행 이 MSIL 스택 프레임에 있는 지역 변수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd582-107">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="cd582-108">[out] 검색된 값을 나타내는 ICorDebugValue 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd582-108">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd582-109">설명</span><span class="sxs-lookup"><span data-stu-id="cd582-109">Remarks</span></span>  

 <span data-ttu-id="cd582-110">`GetLocalVariable`메서드는 MSIL 스택 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd582-110">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd582-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd582-111">Requirements</span></span>  

 <span data-ttu-id="cd582-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd582-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd582-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd582-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd582-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd582-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd582-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd582-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
