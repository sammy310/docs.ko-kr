---
title: ICorPublishAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5de74b52caee27a1a12cff4a7f9165a07e961ce7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072794"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="a5b7a-102">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="a5b7a-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="a5b7a-103">이 표시 되는 응용 프로그램 도메인의 이름을 가져옵니다 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5b7a-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5b7a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a5b7a-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a5b7a-107">[out] 반환 된 null 문자를 포함 하는 와이드 문자의 수에 대 한 포인터를 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5b7a-108">[out] 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5b7a-109">설명</span><span class="sxs-lookup"><span data-stu-id="a5b7a-109">Remarks</span></span>  
 <span data-ttu-id="a5b7a-110">하는 경우 `szName` 가 null이 아닌 합니다 `GetName` 메서드를 복사 `cchName` 문자 (null 종결자 포함)에 `szName`입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="a5b7a-111">반환 된 null이 아닌 경우 `pcchName`, 실제 이름 (null 종결자 포함)의 문자 수에 저장 됩니다는 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="a5b7a-112">`GetName` 메서드 복사 된 문자 수에 관계 없이 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b7a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5b7a-113">Requirements</span></span>  
 <span data-ttu-id="a5b7a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5b7a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5b7a-115">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a5b7a-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a5b7a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5b7a-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a5b7a-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a5b7a-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5b7a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5b7a-118">See also</span></span>

- [<span data-ttu-id="a5b7a-119">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5b7a-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
