---
title: ICorDebugMDA::GetXML 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e78b8a2069671d0fe790956ca914225325a78bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228824"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="83c2f-102">ICorDebugMDA::GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="83c2f-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="83c2f-103">연결 된 MDA (관리 디버깅 도우미)으로 표시 된 전체 XML 스트림을 가져옵니다 [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="83c2f-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c2f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83c2f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="83c2f-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="83c2f-107">[out] XML 스트림의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="83c2f-108">[out] XML 스트림을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="83c2f-109">배열이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c2f-110">설명</span><span class="sxs-lookup"><span data-stu-id="83c2f-110">Remarks</span></span>  
 <span data-ttu-id="83c2f-111">`GetXML` 메서드는 연결 된 XML 스트림의 크기에 따라 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c2f-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c2f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83c2f-112">Requirements</span></span>  
 <span data-ttu-id="83c2f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="83c2f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c2f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83c2f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83c2f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83c2f-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="83c2f-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="83c2f-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83c2f-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="83c2f-117">See also</span></span>

- [<span data-ttu-id="83c2f-118">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c2f-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="83c2f-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="83c2f-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
