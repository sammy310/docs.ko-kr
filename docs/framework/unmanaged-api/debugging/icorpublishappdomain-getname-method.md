---
description: '자세히 알아보기: ICorPublishAppDomain:: GetName 메서드'
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
ms.openlocfilehash: 05b1b14f7e0db371b29059ec3d44333ac40428e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721803"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="4207b-103">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="4207b-103">ICorPublishAppDomain::GetName Method</span></span>

<span data-ttu-id="4207b-104">이 [ICorPublishAppDomain](icorpublishappdomain-interface.md)가 나타내는 응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4207b-104">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4207b-105">구문</span><span class="sxs-lookup"><span data-stu-id="4207b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4207b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4207b-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="4207b-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4207b-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4207b-108">제한이 배열에 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="4207b-108">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="4207b-109">제한이 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4207b-109">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4207b-110">설명</span><span class="sxs-lookup"><span data-stu-id="4207b-110">Remarks</span></span>  

 <span data-ttu-id="4207b-111">`szName`가 null이 아닌 경우이 `GetName` 메서드는 null 종결자를 포함 하 여 최대 자까지로 복사 `cchName` `szName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4207b-111">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="4207b-112">에서 null이 아닌가 반환 되 면 `pcchName` 이름에 있는 실제 문자 수 (null 종결자 포함)가 배열에 저장 됩니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="4207b-112">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="4207b-113">`GetName`메서드는 복사 된 문자 수에 관계 없이 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4207b-113">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4207b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4207b-114">Requirements</span></span>  

 <span data-ttu-id="4207b-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4207b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4207b-116">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="4207b-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4207b-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4207b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4207b-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4207b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4207b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4207b-119">See also</span></span>

- [<span data-ttu-id="4207b-120">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4207b-120">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
