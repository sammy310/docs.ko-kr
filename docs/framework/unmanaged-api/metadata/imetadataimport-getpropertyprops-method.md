---
title: IMetaDataImport::GetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122605"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="375bf-102">IMetaDataImport::GetPropertyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="375bf-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="375bf-103">지정 된 토큰에 의해 표현 되는 속성에 대 한 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="375bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="375bf-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="375bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="375bf-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="375bf-106">[in] 에 대 한 메타 데이터를 반환할 속성을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="375bf-107">[out] 속성을 구현 하는 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="375bf-108">[out] 속성 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="375bf-109">[in] 와이드 문자에서 크기 `szProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="375bf-110">[out] 반환 하는 와이드 문자 수가 `szProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="375bf-111">[out] 속성에 적용할 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="375bf-112">이 값은의 비트 마스크를 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="375bf-113">[out] 속성의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="375bf-114">[out] 반환 된 바이트 수가 `ppvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="375bf-115">[out] 속성의 기본값은 상수의 형식을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="375bf-116">CorElementType 열거형에서이 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="375bf-117">[out] 이 속성의 기본값을 저장 하는 바이트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="375bf-118">[out] 와이드 문자에서 크기 `ppDefaultValue`이면 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING;은 그렇지 않은 경우이 값은 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="375bf-119">이런 경우, 길이의 `ppDefaultValue` 에 지정 된 형식에서 유추 됩니다 `pdwCPlusTypeFlag`합니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="375bf-120">[out] 속성에 대 한 set 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="375bf-121">[out] 속성의 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="375bf-122">[out] 배열 속성에 연결 된 다른 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="375bf-123">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="375bf-124">모든 메서드를 포함할 수 있는 크기 배열의 얻을 수 없는 경우 경고 없이 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="375bf-125">[out] MethodDef 토큰에서 반환 된 수가 `rmdOtherMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="375bf-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="375bf-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="375bf-126">Requirements</span></span>  
 <span data-ttu-id="375bf-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="375bf-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="375bf-128">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="375bf-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="375bf-129">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="375bf-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="375bf-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="375bf-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="375bf-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="375bf-131">See also</span></span>

- [<span data-ttu-id="375bf-132">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="375bf-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="375bf-133">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="375bf-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
