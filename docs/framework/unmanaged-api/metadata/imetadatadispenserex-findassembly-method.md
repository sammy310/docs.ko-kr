---
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
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713394"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="816ce-102">IMetaDataDispenserEx::FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="816ce-102">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="816ce-103">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="816ce-103">This method is not implemented.</span></span> <span data-ttu-id="816ce-104">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="816ce-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="816ce-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="816ce-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="816ce-107">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="816ce-108">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="816ce-109">진행 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="816ce-110">진행 찾을 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="816ce-111">제한이 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="816ce-112">진행 의 크기 (바이트)입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="816ce-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="816ce-113">제한이 에서 실제로 반환 되는 문자 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="816ce-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="816ce-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="816ce-114">Requirements</span></span>  

 <span data-ttu-id="816ce-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="816ce-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816ce-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="816ce-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="816ce-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="816ce-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="816ce-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="816ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816ce-119">참조</span><span class="sxs-lookup"><span data-stu-id="816ce-119">See also</span></span>

- [<span data-ttu-id="816ce-120">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="816ce-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="816ce-121">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="816ce-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
