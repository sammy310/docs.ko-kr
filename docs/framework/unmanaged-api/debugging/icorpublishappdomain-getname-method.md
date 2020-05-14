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
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396292"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="00d48-102">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="00d48-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="00d48-103">이 [ICorPublishAppDomain](icorpublishappdomain-interface.md)가 나타내는 응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00d48-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d48-104">구문</span><span class="sxs-lookup"><span data-stu-id="00d48-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00d48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00d48-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="00d48-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="00d48-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="00d48-107">제한이 배열에 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="00d48-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="00d48-108">제한이 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="00d48-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00d48-109">설명</span><span class="sxs-lookup"><span data-stu-id="00d48-109">Remarks</span></span>  
 <span data-ttu-id="00d48-110">`szName`가 null이 아닌 경우이 `GetName` 메서드는 null 종결자를 포함 하 여 최대 자까지로 복사 `cchName` `szName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d48-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="00d48-111">에서 null이 아닌가 반환 되 면 `pcchName` 이름에 있는 실제 문자 수 (null 종결자 포함)가 배열에 저장 됩니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="00d48-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="00d48-112">`GetName`메서드는 복사 된 문자 수에 관계 없이 S_OK HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d48-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00d48-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00d48-113">Requirements</span></span>  
 <span data-ttu-id="00d48-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00d48-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00d48-115">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="00d48-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="00d48-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00d48-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00d48-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00d48-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d48-118">참조</span><span class="sxs-lookup"><span data-stu-id="00d48-118">See also</span></span>

- [<span data-ttu-id="00d48-119">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00d48-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
