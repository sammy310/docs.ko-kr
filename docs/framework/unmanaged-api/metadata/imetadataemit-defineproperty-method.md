---
title: IMetaDataEmit::DefineProperty 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b80833892fc1c0290e94f5de7d9b081529c6a37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085027"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="45b1a-102">IMetaDataEmit::DefineProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="45b1a-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="45b1a-103">지정 된 지정된 된 형식에 대 한 속성 정의 만듭니다 `get` 및 `set` 메서드 접근자는 속성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45b1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="45b1a-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45b1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45b1a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="45b1a-106">[in] 클래스 또는 속성이 정의 되는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="45b1a-107">[in] 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="45b1a-108">[in] 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="45b1a-109">[in] 속성 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="45b1a-110">[in] 바이트 수가 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="45b1a-111">[in] 형식 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="45b1a-112">[in] 속성에 대 한 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="45b1a-113">[in] \(유니코드) 수의 문자 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="45b1a-114">[in] 속성 값을 설정 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="45b1a-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="45b1a-115">[in] 속성 값을 가져오는 메서드.</span><span class="sxs-lookup"><span data-stu-id="45b1a-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="45b1a-116">[in] 속성과 연결 된 다른 메서드는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="45b1a-117">배열 종료는 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="45b1a-118">[out] `mdProperty` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="45b1a-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45b1a-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45b1a-119">Requirements</span></span>  
 <span data-ttu-id="45b1a-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="45b1a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45b1a-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45b1a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45b1a-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="45b1a-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45b1a-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45b1a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b1a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="45b1a-124">See also</span></span>

- [<span data-ttu-id="45b1a-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45b1a-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="45b1a-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45b1a-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
