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
ms.openlocfilehash: c33ede841324820da16e33d35bbf5e8f8e75924f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009371"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="0a886-102">IMetaDataEmit::DefineSecurityAttributeSet 메서드</span><span class="sxs-lookup"><span data-stu-id="0a886-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="0a886-103">지정 된 토큰이 참조 하는 개체에 연결할 보안 권한 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a886-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a886-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a886-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a886-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a886-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="0a886-106">진행 보안 정보가 연결 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0a886-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="0a886-107">진행 구조체의 배열 `COR_SECATTR` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0a886-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="0a886-108">진행 의 요소 수 `rSecAttrs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0a886-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="0a886-109">제한이 메서드가 실패 하는 경우 문제를 일으킨 요소의 인덱스를 지정 합니다 `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="0a886-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a886-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a886-110">Requirements</span></span>  
 <span data-ttu-id="0a886-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a886-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a886-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0a886-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a886-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a886-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a886-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a886-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a886-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a886-115">See also</span></span>

- [<span data-ttu-id="0a886-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a886-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0a886-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a886-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
