---
title: IMetaDataImport2::EnumMethodSpecs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8cd086a86d104fdfebf1a8298a22b795cb2389b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782642"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="2eca4-102">IMetaDataImport2::EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="2eca4-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="2eca4-103">지정한 MethodDef 또는 MemberRef 연관 MethodSpec 토큰 배열의 토큰 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eca4-104">구문</span><span class="sxs-lookup"><span data-stu-id="2eca4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="2eca4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2eca4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2eca4-106">[out에서] 에 대 한 열거자에 대 한 포인터 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="2eca4-107">[in] 열거할 인 MethodSpec 토큰은 메서드를 나타내는 MemberRef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="2eca4-108">경우 변수의 `tk` 0 (영) 이면 범위에서 모든 MethodSpec 토큰 열거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="2eca4-109">[out] 배열 열거할 MethodSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2eca4-110">[in] 에 배치 하는 토큰의 요청 된 최대 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="2eca4-111">[out] 반환 된 토큰 수 있는 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2eca4-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="2eca4-112">Return Value</span></span>  
  
|<span data-ttu-id="2eca4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2eca4-113">HRESULT</span></span>|<span data-ttu-id="2eca4-114">설명</span><span class="sxs-lookup"><span data-stu-id="2eca4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2eca4-115">`EnumMethodSpecs` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2eca4-116">`phEnum` 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="2eca4-117">이 경우 `pcMethodSpecs` 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eca4-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2eca4-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2eca4-118">Requirements</span></span>  
 <span data-ttu-id="2eca4-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2eca4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eca4-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2eca4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2eca4-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2eca4-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2eca4-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eca4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eca4-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="2eca4-123">See also</span></span>

- [<span data-ttu-id="2eca4-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2eca4-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="2eca4-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2eca4-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
