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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da57ecf0c153d902322798e1927c995a34cb93d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761993"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="fdcfa-102">ICorDebugMDA::GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="fdcfa-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="fdcfa-103">나타내는 관리 디버깅 도우미 (MDA)에 대 한 설명을 포함 하는 문자열을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdcfa-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdcfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdcfa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdcfa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="fdcfa-106">[in] 설명을 저장 하는 문자열 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fdcfa-107">[out] 문자열 버퍼에 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="fdcfa-108">[out] MDA의 설명이 들어 있는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdcfa-109">설명</span><span class="sxs-lookup"><span data-stu-id="fdcfa-109">Remarks</span></span>  
 <span data-ttu-id="fdcfa-110">문자열은 길이가 0 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdcfa-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdcfa-111">Requirements</span></span>  
 <span data-ttu-id="fdcfa-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fdcfa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdcfa-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdcfa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdcfa-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdcfa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdcfa-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdcfa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdcfa-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="fdcfa-116">See also</span></span>

- [<span data-ttu-id="fdcfa-117">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdcfa-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="fdcfa-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="fdcfa-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
