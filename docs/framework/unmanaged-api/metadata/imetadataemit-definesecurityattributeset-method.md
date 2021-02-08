---
description: IMetaDataEmit::D efineSecurityAttributeSet 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 3512857ca23d65389b0e150bd24234d272ddd9b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784056"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="ed7c5-103">IMetaDataEmit::DefineSecurityAttributeSet 메서드</span><span class="sxs-lookup"><span data-stu-id="ed7c5-103">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="ed7c5-104">지정 된 토큰이 참조 하는 개체에 연결할 보안 권한 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-104">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed7c5-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed7c5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed7c5-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="ed7c5-107">진행 보안 정보가 연결 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-107">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="ed7c5-108">진행 구조체의 배열 `COR_SECATTR` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-108">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="ed7c5-109">진행 의 요소 수 `rSecAttrs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-109">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="ed7c5-110">제한이 메서드가 실패 하는 경우 문제를 일으킨 요소의 인덱스를 지정 합니다 `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="ed7c5-110">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed7c5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed7c5-111">Requirements</span></span>  

 <span data-ttu-id="ed7c5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7c5-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ed7c5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed7c5-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed7c5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed7c5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7c5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed7c5-116">See also</span></span>

- [<span data-ttu-id="ed7c5-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed7c5-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ed7c5-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed7c5-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
