---
title: IMetaDataImport2::GetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049858"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="a97e7-102">IMetaDataImport2::GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a97e7-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="a97e7-103">지정된 된 토큰을 나타내는 제네릭 매개 변수를 사용 하 여 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a97e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="a97e7-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a97e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a97e7-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="a97e7-106">[in] 메타 데이터를 반환 하는 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="a97e7-107">[out] 서 수 위치는 `Type` 부모 생성자 또는 메서드 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="a97e7-108">[out] 값을 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 설명 하는 열거형은 `Type` 제네릭 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="a97e7-109">[out] 형식 정의 또는 MethodDef 토큰 매개 변수의 소유자를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="a97e7-110">[out] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="a97e7-111">[out] 제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a97e7-112">[in] 크기는 `wzName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a97e7-113">[out] 반환 된 크기의 와이드 문자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a97e7-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a97e7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a97e7-114">Requirements</span></span>  
 <span data-ttu-id="a97e7-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a97e7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a97e7-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a97e7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a97e7-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a97e7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a97e7-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a97e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97e7-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a97e7-119">See also</span></span>

- [<span data-ttu-id="a97e7-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a97e7-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="a97e7-121">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a97e7-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
