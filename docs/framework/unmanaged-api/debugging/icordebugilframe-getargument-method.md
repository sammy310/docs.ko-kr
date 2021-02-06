---
description: '자세히 알아보기: ICorDebugILFrame:: GetArgument 메서드'
title: ICorDebugILFrame::GetArgument 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: c845f3c07502f3b1ce564833ee6ef98e3305463f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650510"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="e3a63-103">ICorDebugILFrame::GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="e3a63-103">ICorDebugILFrame::GetArgument Method</span></span>

<span data-ttu-id="e3a63-104">이 MSIL (Microsoft 중간 언어) 스택 프레임에서 지정 된 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3a63-104">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a63-105">구문</span><span class="sxs-lookup"><span data-stu-id="e3a63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3a63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3a63-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="e3a63-107">진행 이 MSIL 스택 프레임에 있는 인수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a63-107">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e3a63-108">[out] 검색된 값을 나타내는 ICorDebugValue 개체의 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a63-108">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3a63-109">설명</span><span class="sxs-lookup"><span data-stu-id="e3a63-109">Remarks</span></span>  

 <span data-ttu-id="e3a63-110">`GetArgument`메서드는 MSIL 스택 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a63-110">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a63-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3a63-111">Requirements</span></span>  

 <span data-ttu-id="e3a63-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3a63-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a63-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3a63-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3a63-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3a63-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3a63-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a63-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
