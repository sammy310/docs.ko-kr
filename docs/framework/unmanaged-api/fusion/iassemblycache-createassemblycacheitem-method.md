---
description: '자세한 정보: IAssemblyCache:: CreateAssemblyCacheItem 메서드'
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
ms.openlocfilehash: 3377901d358bcf643ce0d30336c1c0cd8089e50c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760981"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="8b6dc-103">IAssemblyCache::CreateAssemblyCacheItem 메서드</span><span class="sxs-lookup"><span data-stu-id="8b6dc-103">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>

<span data-ttu-id="8b6dc-104">새 [Iassemblycacheitem](iassemblycacheitem-interface.md) 개체에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-104">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b6dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b6dc-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b6dc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b6dc-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="8b6dc-107">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-107">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="8b6dc-108">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="8b6dc-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="8b6dc-109">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="8b6dc-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="8b6dc-110">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8b6dc-111">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-111">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8b6dc-112">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-112">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="8b6dc-113">제한이 반환 된 `IAssemblyCacheItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-113">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="8b6dc-114">[in, 선택 사항] 정규화 되지 않은 쉼표로 구분 된 `name=value` 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-114">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b6dc-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b6dc-115">Requirements</span></span>  

 <span data-ttu-id="8b6dc-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6dc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b6dc-117">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8b6dc-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8b6dc-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b6dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6dc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b6dc-119">See also</span></span>

- [<span data-ttu-id="8b6dc-120">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b6dc-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="8b6dc-121">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b6dc-121">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
