---
title: IAssemblyCache::CreateAssemblyCacheItem 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
ms.openlocfilehash: b417377ea1d0746e563490d87cc9a988e857d943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697040"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="7fc01-102">IAssemblyCache::CreateAssemblyCacheItem 메서드</span><span class="sxs-lookup"><span data-stu-id="7fc01-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>

<span data-ttu-id="7fc01-103">새 [Iassemblycacheitem](iassemblycacheitem-interface.md) 개체에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc01-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fc01-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fc01-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fc01-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="7fc01-106">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="7fc01-107">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="7fc01-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="7fc01-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="7fc01-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="7fc01-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7fc01-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7fc01-111">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="7fc01-112">제한이 반환 된 `IAssemblyCacheItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="7fc01-113">[in, 선택 사항] 정규화 되지 않은 쉼표로 구분 된 `name=value` 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="7fc01-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc01-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fc01-114">Requirements</span></span>  

 <span data-ttu-id="7fc01-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fc01-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc01-116">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7fc01-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7fc01-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc01-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc01-118">참조</span><span class="sxs-lookup"><span data-stu-id="7fc01-118">See also</span></span>

- [<span data-ttu-id="7fc01-119">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc01-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="7fc01-120">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7fc01-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
