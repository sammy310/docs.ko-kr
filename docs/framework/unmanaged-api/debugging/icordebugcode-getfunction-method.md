---
description: '자세히 알아보기: ICorDebugCode:: GetFunction 메서드'
title: ICorDebugCode::GetFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: c90635bf1821d70d6d056d5cbd495ddfa2d2a2ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711208"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="6480b-103">ICorDebugCode::GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="6480b-103">ICorDebugCode::GetFunction Method</span></span>

<span data-ttu-id="6480b-104">이 "ICorDebugCode"와 연결 된 "ICorDebugFunction"를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6480b-104">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6480b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6480b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6480b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6480b-106">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="6480b-107">제한이 함수 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6480b-107">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6480b-108">설명</span><span class="sxs-lookup"><span data-stu-id="6480b-108">Remarks</span></span>  

 <span data-ttu-id="6480b-109">`ICorDebugCode` 및 `ICorDebugFunction` 은 일 대 일 관계를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6480b-109">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6480b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6480b-110">Requirements</span></span>  

 <span data-ttu-id="6480b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6480b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6480b-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6480b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6480b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6480b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6480b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6480b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
