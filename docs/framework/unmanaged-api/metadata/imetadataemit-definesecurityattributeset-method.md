---
title: IMetaDataEmit::DefineSecurityAttributeSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f244d256d3af104d1d0c65769e82a87d6de046e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189016"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="e9e71-102">IMetaDataEmit::DefineSecurityAttributeSet 메서드</span><span class="sxs-lookup"><span data-stu-id="e9e71-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="e9e71-103">지정한 토큰이 참조 하는 개체에 연결할 보안 권한 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9e71-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9e71-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9e71-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9e71-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9e71-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="e9e71-106">[in] 보안 정보가 연결 되는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e71-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="e9e71-107">[in] 배열을 `COR_SECATTR` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e71-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="e9e71-108">[in] 요소 수가 `rSecAttrs`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e71-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="e9e71-109">[out] 메서드가 실패 하는 경우 지정 된 인덱스에 `rSecAttrs` 문제를 발생 시킨 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e71-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9e71-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9e71-110">Requirements</span></span>  
 <span data-ttu-id="e9e71-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9e71-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9e71-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9e71-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9e71-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e9e71-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e9e71-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e9e71-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9e71-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9e71-115">See also</span></span>

- [<span data-ttu-id="e9e71-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9e71-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9e71-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9e71-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
