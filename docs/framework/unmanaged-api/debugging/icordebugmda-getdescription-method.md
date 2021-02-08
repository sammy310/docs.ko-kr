---
description: '자세히 알아보기: ICorDebugMDA:: GetDescription 메서드'
title: ICorDebugMDA::GetDescription 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: 75ee7d0b912c9f0039acc872173f2cbad25fff38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801204"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="9396c-103">ICorDebugMDA::GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="9396c-103">ICorDebugMDA::GetDescription Method</span></span>

<span data-ttu-id="9396c-104">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)에 대 한 설명을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9396c-104">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9396c-105">구문</span><span class="sxs-lookup"><span data-stu-id="9396c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9396c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9396c-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="9396c-107">진행 설명을 저장 하는 문자열 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9396c-107">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9396c-108">제한이 문자열 버퍼에서 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9396c-108">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9396c-109">제한이 MDA에 대 한 설명을 포함 하는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9396c-109">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9396c-110">설명</span><span class="sxs-lookup"><span data-stu-id="9396c-110">Remarks</span></span>  

 <span data-ttu-id="9396c-111">문자열의 길이는 0 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9396c-111">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9396c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9396c-112">Requirements</span></span>  

 <span data-ttu-id="9396c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9396c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9396c-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9396c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9396c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9396c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9396c-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9396c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9396c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9396c-117">See also</span></span>

- [<span data-ttu-id="9396c-118">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9396c-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="9396c-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="9396c-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
