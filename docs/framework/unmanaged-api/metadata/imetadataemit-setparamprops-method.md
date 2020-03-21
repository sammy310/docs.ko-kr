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
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177499"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="06616-102">IMetaDataEmit::SetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="06616-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="06616-103">[IMetaDataEmit::DefineParam에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)대한 사전 호출에 의해 정의된 메서드 매개 변수의 기능을 설정하거나 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="06616-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06616-104">구문</span><span class="sxs-lookup"><span data-stu-id="06616-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="06616-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06616-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="06616-106">【인】 대상 매개 변수에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="06616-107">【인】 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="06616-108">【인】 매개 변수의 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="06616-109">【인】 상수 값에 대한 ELEMENT_TYPE_\*입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="06616-110">【인】 매개 변수의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="06616-111">【인】 의 (유니코드) 문자의 `pValue`크기입니다.</span><span class="sxs-lookup"><span data-stu-id="06616-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06616-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06616-112">Requirements</span></span>  
 <span data-ttu-id="06616-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06616-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06616-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="06616-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06616-115">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="06616-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06616-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06616-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06616-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06616-117">See also</span></span>

- [<span data-ttu-id="06616-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06616-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="06616-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06616-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
