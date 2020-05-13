---
title: ICorDebugFunction::GetCurrentVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212908"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="d69c1-102">ICorDebugFunction::GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="d69c1-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="d69c1-103">이 ICorDebugFunction 개체로 표시 되는 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d69c1-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="d69c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d69c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d69c1-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="d69c1-106">제한이 이 함수에 대 한 최신 편집의 버전 번호를 나타내는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d69c1-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d69c1-107">설명</span><span class="sxs-lookup"><span data-stu-id="d69c1-107">Remarks</span></span>  
 <span data-ttu-id="d69c1-108">이 함수에 대 한 최신 편집의 버전 번호는 함수 자체의 버전 번호 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d69c1-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="d69c1-109">[ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) 메서드 또는 [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) 메서드 중 하나를 사용 하 여 함수의 버전 번호를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d69c1-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d69c1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d69c1-110">Requirements</span></span>  
 <span data-ttu-id="d69c1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d69c1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d69c1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d69c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d69c1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d69c1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d69c1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d69c1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
