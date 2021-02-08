---
description: '자세히 알아보기: IMetaDataEmit:: SetParamProps 메서드'
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
ms.openlocfilehash: 35e839b05b3671c6c09f315ac636971c386e766e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772026"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="7bc29-103">IMetaDataEmit::SetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7bc29-103">IMetaDataEmit::SetParamProps Method</span></span>

<span data-ttu-id="7bc29-104">[IMetaDataEmit::D efineParam](imetadataemit-defineparam-method.md)에 대 한 이전 호출로 정의 된 메서드 매개 변수의 기능을 설정 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-104">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc29-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bc29-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7bc29-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bc29-106">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="7bc29-107">진행 대상 매개 변수에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-107">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="7bc29-108">진행 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="7bc29-109">진행 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-109">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7bc29-110">진행 상수 값에 대 한 ELEMENT_TYPE_ \*입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-110">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7bc29-111">진행 매개 변수에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-111">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7bc29-112">진행 의 (유니코드) 문자 크기입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="7bc29-112">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc29-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bc29-113">Requirements</span></span>  

 <span data-ttu-id="7bc29-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bc29-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc29-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7bc29-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bc29-116">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bc29-116">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bc29-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc29-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc29-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bc29-118">See also</span></span>

- [<span data-ttu-id="7bc29-119">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bc29-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7bc29-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bc29-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
