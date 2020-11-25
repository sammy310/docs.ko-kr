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
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721064"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="c3a26-102">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a26-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="c3a26-103">전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3a26-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3a26-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c3a26-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c3a26-105">Methods</span></span>  
  
|<span data-ttu-id="c3a26-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c3a26-106">Method</span></span>|<span data-ttu-id="c3a26-107">설명</span><span class="sxs-lookup"><span data-stu-id="c3a26-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3a26-108">GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="c3a26-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="c3a26-109">이에 포함 된 다음에 대 한 포인터를 가져옵니다 `IInstallReferenceItem` `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="c3a26-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3a26-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3a26-110">Requirements</span></span>  

 <span data-ttu-id="c3a26-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3a26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3a26-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c3a26-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c3a26-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a26-114">참조</span><span class="sxs-lookup"><span data-stu-id="c3a26-114">See also</span></span>

- [<span data-ttu-id="c3a26-115">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a26-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c3a26-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3a26-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
