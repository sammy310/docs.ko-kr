---
description: '자세히 알아보기: ICorDebugMDA:: GetName 메서드'
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
ms.openlocfilehash: 4ea39f062071073684a20d8f60875fbaaab43a2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801168"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="19a8c-103">ICorDebugMDA::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="19a8c-103">ICorDebugMDA::GetName Method</span></span>

<span data-ttu-id="19a8c-104">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)의 이름을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-104">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a8c-105">구문</span><span class="sxs-lookup"><span data-stu-id="19a8c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19a8c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19a8c-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="19a8c-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="19a8c-108">제한이 이름 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-108">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="19a8c-109">제한이 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-109">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19a8c-110">설명</span><span class="sxs-lookup"><span data-stu-id="19a8c-110">Remarks</span></span>  

 <span data-ttu-id="19a8c-111">MDA 이름은 고유한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-111">MDA names are unique values.</span></span> <span data-ttu-id="19a8c-112">`GetName`메서드는 XML 스트림을 가져오고 스키마에 따라 스트림에서 이름을 추출 하는 데 편리한 성능 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="19a8c-112">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19a8c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19a8c-113">Requirements</span></span>  

 <span data-ttu-id="19a8c-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19a8c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19a8c-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19a8c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19a8c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19a8c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19a8c-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19a8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a8c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19a8c-118">See also</span></span>

- [<span data-ttu-id="19a8c-119">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19a8c-119">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="19a8c-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="19a8c-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
