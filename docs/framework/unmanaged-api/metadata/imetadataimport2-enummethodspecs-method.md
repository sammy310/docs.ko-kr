---
description: '자세히 알아보기: IMetaDataImport2:: EnumMethodSpecs 메서드'
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
ms.openlocfilehash: 19fff1d78599d968bb1fd0ab27b0f71e41fae20b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677524"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="25d3f-103">IMetaDataImport2::EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="25d3f-103">IMetaDataImport2::EnumMethodSpecs Method</span></span>

<span data-ttu-id="25d3f-104">지정 된 MethodDef 또는 MemberRef 토큰과 연결 된 MethodSpec 토큰 배열의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-104">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d3f-105">구문</span><span class="sxs-lookup"><span data-stu-id="25d3f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="25d3f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25d3f-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="25d3f-107">[in, out] 열거자에 대 한 포인터 `rMethodSpecs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-107">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="25d3f-108">진행 MethodSpec 토큰이 열거 될 메서드를 나타내는 MemberRef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-108">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="25d3f-109">의 값 `tk` 이 0 인 경우 범위의 모든 MethodSpec 토큰이 열거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-109">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="25d3f-110">제한이 열거할 MethodSpec 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-110">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="25d3f-111">진행 에 저장할 요청 된 최대 토큰 수 `rMethodSpecs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-111">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="25d3f-112">제한이 에 배치 된 반환 된 토큰 수 `rMethodSpecs` 입니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-112">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25d3f-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="25d3f-113">Return Value</span></span>  
  
|<span data-ttu-id="25d3f-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25d3f-114">HRESULT</span></span>|<span data-ttu-id="25d3f-115">설명</span><span class="sxs-lookup"><span data-stu-id="25d3f-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="25d3f-116">`EnumMethodSpecs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-116">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="25d3f-117">`phEnum` 에는 멤버 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-117">`phEnum` has no member elements.</span></span> <span data-ttu-id="25d3f-118">이 경우 `pcMethodSpecs` 은 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-118">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25d3f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25d3f-119">Requirements</span></span>  

 <span data-ttu-id="25d3f-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25d3f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25d3f-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="25d3f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25d3f-122">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d3f-122">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25d3f-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25d3f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d3f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25d3f-124">See also</span></span>

- [<span data-ttu-id="25d3f-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25d3f-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="25d3f-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25d3f-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
