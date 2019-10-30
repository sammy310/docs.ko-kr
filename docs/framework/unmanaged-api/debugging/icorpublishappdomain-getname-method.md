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
ms.openlocfilehash: 2f91891164f1f80617cab10347eb4a7a08762c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140344"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="44d52-102">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="44d52-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="44d52-103">이 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)가 나타내는 응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d52-104">구문</span><span class="sxs-lookup"><span data-stu-id="44d52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44d52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44d52-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="44d52-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="44d52-107">제한이 `szName` 배열에 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="44d52-108">제한이 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d52-109">주의</span><span class="sxs-lookup"><span data-stu-id="44d52-109">Remarks</span></span>  
 <span data-ttu-id="44d52-110">`szName` null이 아닌 경우 `GetName` 메서드는 최대 `cchName` 문자 (null 종결자 포함)를 `szName`로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="44d52-111">`pcchName`에서 null이 아닌이 반환 되는 경우에는 이름 (null 종결자 포함)의 실제 문자 수가 `szName` 배열에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="44d52-112">`GetName` 메서드는 복사 된 문자 수에 관계 없이 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44d52-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d52-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44d52-113">Requirements</span></span>  
 <span data-ttu-id="44d52-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d52-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d52-115">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="44d52-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="44d52-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d52-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44d52-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d52-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d52-118">참조</span><span class="sxs-lookup"><span data-stu-id="44d52-118">See also</span></span>

- [<span data-ttu-id="44d52-119">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44d52-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
