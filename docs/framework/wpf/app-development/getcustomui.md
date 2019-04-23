---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191252"
---
# <a name="getcustomui"></a><span data-ttu-id="1bda5-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="1bda5-102">GetCustomUI</span></span>
<span data-ttu-id="1bda5-103">구현 하는 경우 호스트에서 사용자 지정 진행률 및 오류 메시지를 가져오려는 PresentationHost.exe에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bda5-104">구문</span><span class="sxs-lookup"><span data-stu-id="1bda5-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bda5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bda5-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="1bda5-106">[out] 호스트 제공 진행률 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="1bda5-107">[out] 가급적 호스트 제공 진행률 사용자 인터페이스는 클래스의 이름을 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 파일을 <xref:System.Windows.Controls.Page> 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="1bda5-108">이 클래스가 지정 된 어셈블리에 있는 `pwzProgressAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="1bda5-109">[out] 호스트 제공 오류 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="1bda5-110">[out] 호스트 제공 오류 사용자 클래스의 이름을 인터페이스를 가급적 사용 하 여 XAML 파일 <xref:System.Windows.Controls.Page> 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="1bda5-111">이 클래스가 지정 된 어셈블리에 있는 `pwzErrorAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1bda5-112">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="1bda5-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="1bda5-113">HRESULT: 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bda5-114">설명</span><span class="sxs-lookup"><span data-stu-id="1bda5-114">Remarks</span></span>  
 <span data-ttu-id="1bda5-115">호스트 응용 프로그램을 PresentationHost.exe의 기본 사용자 인터페이스를 준수 하지 않는 하는 특정 테마에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="1bda5-116">이 경우 호스트 응용 프로그램 구현할 수 있습니다 [GetCustomUI](getcustomui.md) 를 PresentationHost.exe에 진행률 및 오류 사용자 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="1bda5-117">PresentationHost.exe가 항상 호출 [GetCustomUI](getcustomui.md) 해당 기본 사용자 인터페이스를 사용 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="1bda5-118">이 함수는 PresentationHost의 초기화 중에 한 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bda5-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bda5-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="1bda5-119">See also</span></span>

- [<span data-ttu-id="1bda5-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="1bda5-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
