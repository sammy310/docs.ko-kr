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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178411"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="f5a4b-102">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="f5a4b-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="f5a4b-103">이 [ICorPublishAppDomain로](icorpublishappdomain-interface.md)표시되는 응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a4b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5a4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a4b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5a4b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f5a4b-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f5a4b-107">【아웃】 `szName` null 문자를 포함하여 와이드 문자 수에 대한 포인터는 배열에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="f5a4b-108">【아웃】 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a4b-109">설명</span><span class="sxs-lookup"><span data-stu-id="f5a4b-109">Remarks</span></span>  
 <span data-ttu-id="f5a4b-110">null이 아닌 `szName` 경우 `GetName` 메서드는 null `cchName` 종사 포함 문자까지 `szName`복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="f5a4b-111">null이 반환되는 `pcchName`경우 이름의 실제 문자 수(null 종사 포함)가 배열에 `szName` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="f5a4b-112">메서드는 `GetName` 복사된 문자 수에 관계없이 S_OK HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a4b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5a4b-113">Requirements</span></span>  
 <span data-ttu-id="f5a4b-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a4b-115">**헤더:** 코르펍.idl, 코르펍.h</span><span class="sxs-lookup"><span data-stu-id="f5a4b-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f5a4b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a4b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a4b-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a4b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a4b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5a4b-118">See also</span></span>

- [<span data-ttu-id="f5a4b-119">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5a4b-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
