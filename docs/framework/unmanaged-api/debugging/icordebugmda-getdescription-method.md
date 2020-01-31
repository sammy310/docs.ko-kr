---
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
ms.openlocfilehash: e3744cbfa08de30c53f15c457034b50e2fc5d283
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793244"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="25533-102">ICorDebugMDA::GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="25533-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="25533-103">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)에 대 한 설명을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25533-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25533-104">구문</span><span class="sxs-lookup"><span data-stu-id="25533-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25533-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25533-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="25533-106">진행 설명을 저장 하는 문자열 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="25533-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="25533-107">제한이 문자열 버퍼에서 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25533-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="25533-108">제한이 MDA에 대 한 설명을 포함 하는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="25533-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25533-109">주의</span><span class="sxs-lookup"><span data-stu-id="25533-109">Remarks</span></span>  
 <span data-ttu-id="25533-110">문자열의 길이는 0 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25533-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25533-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25533-111">Requirements</span></span>  
 <span data-ttu-id="25533-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25533-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25533-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25533-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25533-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25533-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25533-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25533-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25533-116">참조</span><span class="sxs-lookup"><span data-stu-id="25533-116">See also</span></span>

- [<span data-ttu-id="25533-117">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25533-117">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="25533-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="25533-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
