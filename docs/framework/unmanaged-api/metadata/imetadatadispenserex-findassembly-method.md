---
description: '자세히 알아보기: IMetaDataDispenserEx:: FindAssembly 메서드'
title: IMetaDataDispenserEx::FindAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 6bed016e9235281b42f5a3231ef2aff284b6cc3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753603"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="4f547-103">IMetaDataDispenserEx::FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="4f547-103">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="4f547-104">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="4f547-104">This method is not implemented.</span></span> <span data-ttu-id="4f547-105">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f547-106">구문</span><span class="sxs-lookup"><span data-stu-id="4f547-106">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f547-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f547-107">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="4f547-108">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-108">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="4f547-109">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-109">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="4f547-110">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-110">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="4f547-111">진행 찾을 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f547-112">제한이 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4f547-113">진행 의 크기 (바이트)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="4f547-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="4f547-114">제한이 에서 실제로 반환 되는 문자 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="4f547-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f547-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f547-115">Requirements</span></span>  

 <span data-ttu-id="4f547-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f547-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f547-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4f547-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f547-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f547-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f547-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f547-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f547-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f547-120">See also</span></span>

- [<span data-ttu-id="4f547-121">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f547-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="4f547-122">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f547-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
