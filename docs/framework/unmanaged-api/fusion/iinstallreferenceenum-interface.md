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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35faeb69e864a428dc40394ad89a7d50b95bbcab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103333"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="e4e79-102">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4e79-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="e4e79-103">참조 된 어셈블리가 전역 어셈블리 캐시에 설치에 대 한 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4e79-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e79-104">구문</span><span class="sxs-lookup"><span data-stu-id="e4e79-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e4e79-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e4e79-105">Methods</span></span>  
  
|<span data-ttu-id="e4e79-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e4e79-106">Method</span></span>|<span data-ttu-id="e4e79-107">설명</span><span class="sxs-lookup"><span data-stu-id="e4e79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4e79-108">GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e4e79-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="e4e79-109">다음에 대 한 포인터를 가져옵니다 `IInstallReferenceItem` 이 포함 된 `IInstallReferenceEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e79-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4e79-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4e79-110">Requirements</span></span>  
 <span data-ttu-id="e4e79-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4e79-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4e79-112">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e4e79-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e4e79-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e79-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4e79-114">See also</span></span>

- [<span data-ttu-id="e4e79-115">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4e79-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="e4e79-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4e79-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
