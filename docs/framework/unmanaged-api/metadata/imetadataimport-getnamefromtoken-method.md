---
title: IMetaDataImport::GetNameFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f45c89572362f380997e7d8247b93c0f8629655
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478874"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="f63b7-102">IMetaDataImport::GetNameFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="f63b7-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="f63b7-103">지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="f63b7-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="f63b7-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f63b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f63b7-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f63b7-107">[in] 에 대 한 이름을 반환할 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="f63b7-108">[out] 힙에 있는 u t F-8 개체 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f63b7-109">설명</span><span class="sxs-lookup"><span data-stu-id="f63b7-109">Remarks</span></span>  
 <span data-ttu-id="f63b7-110">`GetNameFromToken`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="f63b7-111">대신 특정 형식의 토큰이 필요한 경우와 같은 속성을 가져오는 메서드를 호출 `GetFieldProps` 필드에 대해 또는 `GetMethodProps` 메서드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63b7-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f63b7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f63b7-112">Requirements</span></span>  
 <span data-ttu-id="f63b7-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f63b7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f63b7-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f63b7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f63b7-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f63b7-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f63b7-116">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f63b7-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63b7-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f63b7-117">See also</span></span>
- [<span data-ttu-id="f63b7-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63b7-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f63b7-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63b7-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
