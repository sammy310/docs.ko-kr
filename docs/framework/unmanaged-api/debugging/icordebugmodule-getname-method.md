---
description: '자세히 알아보기: ICorDebugModule:: GetName 메서드'
title: ICorDebugModule::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: 0f81271b2be283621027f4c835b6f220a383d771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660197"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="c27a8-103">ICorDebugModule::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="c27a8-103">ICorDebugModule::GetName Method</span></span>

<span data-ttu-id="c27a8-104">모듈의 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-104">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c27a8-105">구문</span><span class="sxs-lookup"><span data-stu-id="c27a8-105">Syntax</span></span>  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c27a8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c27a8-106">Parameters</span></span>  

 `cchname`  
 <span data-ttu-id="c27a8-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c27a8-108">진행 반환 된 이름의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-108">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="c27a8-109">제한이 반환 된 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-109">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c27a8-110">설명</span><span class="sxs-lookup"><span data-stu-id="c27a8-110">Remarks</span></span>  

 <span data-ttu-id="c27a8-111">`GetName`모듈의 파일 이름이 디스크의 이름과 일치 하는 경우 메서드는 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-111">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="c27a8-112">`GetName` 동적 또는 메모리 내 모듈의 경우와 같이 이름을 구성한 경우에는 S_FALSE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27a8-112">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c27a8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c27a8-113">Requirements</span></span>  

 <span data-ttu-id="c27a8-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c27a8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c27a8-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c27a8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c27a8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c27a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c27a8-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c27a8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27a8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c27a8-118">See also</span></span>
