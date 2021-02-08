---
description: '자세한 정보: IInstallReferenceEnum 인터페이스'
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
ms.openlocfilehash: 496bd508b95b51cb23949f32f8390c7cb733b37e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800104"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="939d8-103">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="939d8-103">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="939d8-104">전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="939d8-104">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="939d8-105">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="939d8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="939d8-106">Methods</span></span>  
  
|<span data-ttu-id="939d8-107">메서드</span><span class="sxs-lookup"><span data-stu-id="939d8-107">Method</span></span>|<span data-ttu-id="939d8-108">설명</span><span class="sxs-lookup"><span data-stu-id="939d8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="939d8-109">GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="939d8-109">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="939d8-110">이에 포함 된 다음에 대 한 포인터를 가져옵니다 `IInstallReferenceItem` `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="939d8-110">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="939d8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="939d8-111">Requirements</span></span>  

 <span data-ttu-id="939d8-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="939d8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="939d8-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="939d8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="939d8-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="939d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939d8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="939d8-115">See also</span></span>

- [<span data-ttu-id="939d8-116">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="939d8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="939d8-117">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="939d8-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
