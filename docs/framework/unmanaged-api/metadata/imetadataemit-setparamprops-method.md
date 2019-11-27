---
title: IMetaDataEmit::SetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 813460aa027b259866b168d426fd28502b5c4465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432503"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="2cd20-102">IMetaDataEmit::SetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="2cd20-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="2cd20-103">[IMetaDataEmit::D efineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)에 대 한 이전 호출로 정의 된 메서드 매개 변수의 기능을 설정 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd20-104">구문</span><span class="sxs-lookup"><span data-stu-id="2cd20-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cd20-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2cd20-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="2cd20-106">진행 대상 매개 변수에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="2cd20-107">진행 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2cd20-108">진행 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2cd20-109">진행 상수 값에 대 한 ELEMENT_TYPE_ \*입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2cd20-110">진행 매개 변수에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2cd20-111">진행 `pValue`의 (유니코드) 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cd20-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cd20-112">Requirements</span></span>  
 <span data-ttu-id="2cd20-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cd20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cd20-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2cd20-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cd20-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd20-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cd20-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cd20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd20-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2cd20-117">See also</span></span>

- [<span data-ttu-id="2cd20-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cd20-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2cd20-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cd20-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
