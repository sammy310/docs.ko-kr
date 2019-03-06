---
title: Activate 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357276"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b5201-102">Activate 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b5201-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b5201-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5201-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b5201-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5201-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5201-105">구문</span><span class="sxs-lookup"><span data-stu-id="b5201-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5201-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5201-106">Parameters</span></span>  
 <span data-ttu-id="b5201-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="b5201-107">pParameters</span></span>  
 <span data-ttu-id="b5201-108">활성화 매개 변수 창에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5201-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="b5201-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="b5201-109">ppInner</span></span>  
 <span data-ttu-id="b5201-110">에 대 한 포인터를 포함 하는 단일 요소 버퍼의 주소에 대 한 포인터를 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b5201-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5201-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5201-111">Requirements</span></span>  
 <span data-ttu-id="b5201-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5201-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5201-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="b5201-113">**DLL:**</span></span>  
  
 <span data-ttu-id="b5201-114">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="b5201-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b5201-115">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b5201-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b5201-116">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5201-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5201-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5201-117">See also</span></span>
- [<span data-ttu-id="b5201-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="b5201-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
