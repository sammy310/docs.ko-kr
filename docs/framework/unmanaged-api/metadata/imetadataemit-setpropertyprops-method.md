---
title: IMetaDataEmit::SetPropertyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177472"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="5c3df-102">IMetaDataEmit::SetPropertyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5c3df-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="5c3df-103">[정의 속성 메서드에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)대 한 이전 호출에 의해 정의 된 속성에 대 한 메타 데이터에 저장 된 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3df-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c3df-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c3df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c3df-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="5c3df-106">【인】 속성을 변경할 토큰</span><span class="sxs-lookup"><span data-stu-id="5c3df-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="5c3df-107">【인】 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5c3df-108">【인】 속성의 기본값의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5c3df-109">【인】 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5c3df-110">【인】 에서 (유니코드) 문자의 `pValue`수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="5c3df-111">【인】 속성 값을 설정하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="5c3df-112">【인】 속성 값을 얻는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="5c3df-113">【인】 속성과 연결된 다른 메서드의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="5c3df-114">토큰으로 이 `mdTokenNil` 배열을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="5c3df-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3df-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c3df-115">Requirements</span></span>  
 <span data-ttu-id="5c3df-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c3df-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3df-117">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="5c3df-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c3df-118">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5c3df-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c3df-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c3df-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3df-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c3df-120">See also</span></span>

- [<span data-ttu-id="5c3df-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c3df-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5c3df-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c3df-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
