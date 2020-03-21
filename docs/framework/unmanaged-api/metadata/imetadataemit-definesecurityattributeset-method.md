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
ms.openlocfilehash: fadd1974cd4fa8a51a06700835f46df24e37d7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175774"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="92c43-102">IMetaDataEmit::DefineSecurityAttributeSet 메서드</span><span class="sxs-lookup"><span data-stu-id="92c43-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="92c43-103">지정된 토큰에서 참조하는 개체에 연결할 보안 권한 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="92c43-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c43-104">구문</span><span class="sxs-lookup"><span data-stu-id="92c43-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92c43-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="92c43-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="92c43-106">【인】 보안 정보가 첨부되는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="92c43-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="92c43-107">【인】 구조의 `COR_SECATTR` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="92c43-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="92c43-108">【인】 의 요소 수입니다. `rSecAttrs`</span><span class="sxs-lookup"><span data-stu-id="92c43-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="92c43-109">【아웃】 메서드가 실패하면 문제를 일으킨 `rSecAttrs` 요소의 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92c43-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c43-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="92c43-110">Requirements</span></span>  
 <span data-ttu-id="92c43-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92c43-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c43-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="92c43-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92c43-113">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="92c43-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92c43-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c43-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c43-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92c43-115">See also</span></span>

- [<span data-ttu-id="92c43-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92c43-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="92c43-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="92c43-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
