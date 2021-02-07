---
description: '자세히 알아보기: ICorDebugFunction:: GetCurrentVersionNumber 메서드'
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
ms.openlocfilehash: ccc96755ac74624a00b806e3f569f39f2d6059f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692539"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="fe640-103">ICorDebugFunction::GetCurrentVersionNumber 메서드</span><span class="sxs-lookup"><span data-stu-id="fe640-103">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>

<span data-ttu-id="fe640-104">이 ICorDebugFunction 개체로 표시 되는 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe640-104">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe640-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe640-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe640-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe640-106">Parameters</span></span>  

 `pnCurrentVersion`  
 <span data-ttu-id="fe640-107">제한이 이 함수에 대 한 최신 편집의 버전 번호를 나타내는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fe640-107">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe640-108">설명</span><span class="sxs-lookup"><span data-stu-id="fe640-108">Remarks</span></span>  

 <span data-ttu-id="fe640-109">이 함수에 대 한 최신 편집의 버전 번호는 함수 자체의 버전 번호 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe640-109">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="fe640-110">[ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) 메서드 또는 [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) 메서드 중 하나를 사용 하 여 함수의 버전 번호를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe640-110">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe640-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe640-111">Requirements</span></span>  

 <span data-ttu-id="fe640-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe640-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe640-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe640-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe640-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe640-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe640-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe640-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
