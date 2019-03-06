---
title: ICorDebugMDA::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f0ed1aa0d095b13a90ed5b036719e71ccc8e272
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468197"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="41893-102">ICorDebugMDA::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="41893-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="41893-103">관리 디버깅 도우미 (MDA)의 이름을 나타내는 문자열을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41893-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41893-104">구문</span><span class="sxs-lookup"><span data-stu-id="41893-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41893-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41893-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="41893-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="41893-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="41893-107">[out] 이름의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="41893-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="41893-108">[out] 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="41893-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41893-109">설명</span><span class="sxs-lookup"><span data-stu-id="41893-109">Remarks</span></span>  
 <span data-ttu-id="41893-110">MDA 이름은 고유 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41893-110">MDA names are unique values.</span></span> <span data-ttu-id="41893-111">`GetName` 메서드는 XML 스트림을 가져오는 스키마를 기반으로 하는 스트림의 이름을 추출 하는 편리한 성능 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="41893-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41893-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41893-112">Requirements</span></span>  
 <span data-ttu-id="41893-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41893-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41893-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41893-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41893-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41893-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41893-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41893-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41893-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="41893-117">See also</span></span>
- [<span data-ttu-id="41893-118">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41893-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="41893-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="41893-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
