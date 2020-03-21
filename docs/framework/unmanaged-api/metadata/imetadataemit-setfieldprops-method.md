---
title: IMetaDataEmit::SetFieldProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177558"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="ab26d-102">IMetaDataEmit::SetFieldProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ab26d-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="ab26d-103">지정된 필드 토큰에서 참조하는 필드의 기본값을 설정하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab26d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab26d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab26d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab26d-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="ab26d-106">【인】 대상 필드에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="ab26d-107">【인】 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-107">[in] Field attributes.</span></span> <span data-ttu-id="ab26d-108">이것은 값의 `CorFieldAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ab26d-109">【인】 `ELEMENT_TYPE_` 에 대 한 상수 값입니다. *\**</span><span class="sxs-lookup"><span data-stu-id="ab26d-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="ab26d-110">이것은 값입니다. `CorElementType`</span><span class="sxs-lookup"><span data-stu-id="ab26d-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="ab26d-111">상수가 정의되지 않은 경우 이 `ELEMENT_TYPE_END`값을 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ab26d-112">【인】 필드의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab26d-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ab26d-113">【인】 유니코드 문자의 크기입니다. `pValue`</span><span class="sxs-lookup"><span data-stu-id="ab26d-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab26d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab26d-114">Requirements</span></span>  
 <span data-ttu-id="ab26d-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab26d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab26d-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="ab26d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab26d-117">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ab26d-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab26d-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab26d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab26d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab26d-119">See also</span></span>

- [<span data-ttu-id="ab26d-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab26d-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ab26d-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab26d-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
