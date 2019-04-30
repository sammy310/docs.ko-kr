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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992487"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="3c3a6-102">IMetaDataEmit::SetFieldProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3c3a6-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="3c3a6-103">설정 하거나 지정 된 필드 토큰에서 참조 하는 필드에 대 한 기본 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c3a6-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c3a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c3a6-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="3c3a6-106">[in] 대상 필드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="3c3a6-107">[in] 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-107">[in] Field attributes.</span></span> <span data-ttu-id="3c3a6-108">이 비트 마스크의 `CorFieldAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="3c3a6-109">[in] 합니다 `ELEMENT_TYPE_` *\** 상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="3c3a6-110">이 `CorElementType` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="3c3a6-111">이 값을 설정 하는 상수를 정의 하지 않은 경우 `ELEMENT_TYPE_END`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3c3a6-112">[in] 필드의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="3c3a6-113">[in] 유니코드 문자에서 크기의 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3a6-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c3a6-114">Requirements</span></span>  
 <span data-ttu-id="3c3a6-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c3a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3a6-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c3a6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c3a6-117">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3c3a6-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c3a6-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3a6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3a6-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c3a6-119">See also</span></span>

- [<span data-ttu-id="3c3a6-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c3a6-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3c3a6-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c3a6-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
