---
title: LoadFromHistory 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084976"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="26d82-102">LoadFromHistory 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="26d82-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="26d82-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26d82-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="26d82-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d82-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d82-105">구문</span><span class="sxs-lookup"><span data-stu-id="26d82-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="26d82-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="26d82-106">Parameters</span></span>  
 <span data-ttu-id="26d82-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="26d82-107">pHistoryStream</span></span>  
 <span data-ttu-id="26d82-108">기록 정보 스트림으로 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="26d82-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="26d82-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="26d82-109">pBindCtx</span></span>  
 <span data-ttu-id="26d82-110">바인드 컨텍스트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="26d82-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26d82-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="26d82-111">Requirements</span></span>  
 <span data-ttu-id="26d82-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26d82-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26d82-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="26d82-113">**DLL:**</span></span>  
  
 <span data-ttu-id="26d82-114">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="26d82-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="26d82-115">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="26d82-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="26d82-116">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26d82-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d82-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="26d82-117">See also</span></span>

- [<span data-ttu-id="26d82-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="26d82-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
