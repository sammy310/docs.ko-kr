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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175332"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="e55fd-102">IMetaDataImport::GetPropertyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e55fd-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="e55fd-103">지정된 토큰으로 표시되는 속성의 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="e55fd-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="e55fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e55fd-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="e55fd-106">【인】 메타데이터를 반환하는 속성을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="e55fd-107">【아웃】 속성을 구현하는 형식을 나타내는 TypeDef 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="e55fd-108">【아웃】 속성 이름을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="e55fd-109">【인】 의 와이드 문자의 `szProperty`크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="e55fd-110">【아웃】 에서 반환되는 와이드 `szProperty`문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="e55fd-111">【아웃】 속성에 적용 된 모든 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="e55fd-112">이 값은 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="e55fd-113">【아웃】 속성의 메타데이터 서명에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="e55fd-114">【아웃】 에서 반환되는 바이트 `ppvSig`수입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="e55fd-115">【아웃】 속성의 기본값인 상수의 형식을 지정하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="e55fd-116">이 값은 CorElementType 열거형에서 발원합니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="e55fd-117">【아웃】 이 속성의 기본값을 저장하는 바이트에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="e55fd-118">【아웃】 의 넓은 문자의 `ppDefaultValue`크기는 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING. 그렇지 않으면 이 값은 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="e55fd-119">이 경우 `ppDefaultValue` 길이는 에 의해 `pdwCPlusTypeFlag`지정된 형식에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="e55fd-120">【아웃】 속성에 대 한 집합 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="e55fd-121">【아웃】 속성에 대 한 get 접근자 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="e55fd-122">【아웃】 속성과 연결된 다른 메서드를 나타내는 MethodDef 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e55fd-123">[in] `rmdOtherMethod` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="e55fd-124">모든 메서드를 보유할 수 있을 만큼 큰 배열을 제공하지 않으면 경고 없이 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="e55fd-125">【아웃】 에서 반환되는 MethodDef 토큰 `rmdOtherMethod`수입니다.</span><span class="sxs-lookup"><span data-stu-id="e55fd-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55fd-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e55fd-126">Requirements</span></span>  
 <span data-ttu-id="e55fd-127">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e55fd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55fd-128">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="e55fd-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e55fd-129">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e55fd-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e55fd-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55fd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55fd-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e55fd-131">See also</span></span>

- [<span data-ttu-id="e55fd-132">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e55fd-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e55fd-133">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e55fd-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
