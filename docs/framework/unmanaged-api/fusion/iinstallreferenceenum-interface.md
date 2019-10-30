---
title: IInstallReferenceEnum 인터페이스
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: d3f7c24b4bd373924c44dbc0490c890e7f1322bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131729"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="e3638-102">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3638-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="e3638-103">전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3638-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3638-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3638-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e3638-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e3638-105">Methods</span></span>  
  
|<span data-ttu-id="e3638-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e3638-106">Method</span></span>|<span data-ttu-id="e3638-107">설명</span><span class="sxs-lookup"><span data-stu-id="e3638-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3638-108">GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e3638-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="e3638-109">이 `IInstallReferenceEnum`에 포함 된 다음 `IInstallReferenceItem`에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3638-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3638-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3638-110">Requirements</span></span>  
 <span data-ttu-id="e3638-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3638-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3638-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e3638-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e3638-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3638-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3638-114">참조</span><span class="sxs-lookup"><span data-stu-id="e3638-114">See also</span></span>

- [<span data-ttu-id="e3638-115">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3638-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e3638-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3638-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
