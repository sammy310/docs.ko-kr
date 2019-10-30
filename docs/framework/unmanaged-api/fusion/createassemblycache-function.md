---
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108861"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="74633-102">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="74633-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="74633-103">전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74633-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74633-104">구문</span><span class="sxs-lookup"><span data-stu-id="74633-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="74633-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74633-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="74633-106">제한이 반환 된 `IAssemblyCache` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74633-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="74633-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74633-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="74633-108">`dwReserved` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74633-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74633-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74633-109">Requirements</span></span>  
 <span data-ttu-id="74633-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74633-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74633-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="74633-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="74633-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74633-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74633-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74633-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74633-114">참조</span><span class="sxs-lookup"><span data-stu-id="74633-114">See also</span></span>

- [<span data-ttu-id="74633-115">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74633-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="74633-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="74633-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="74633-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="74633-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
