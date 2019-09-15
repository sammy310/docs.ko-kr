---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991371"
---
# <a name="getcustomui"></a><span data-ttu-id="d7b3b-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="d7b3b-102">GetCustomUI</span></span>
<span data-ttu-id="d7b3b-103">구현 된 경우 호스트에서 사용자 지정 진행률 및 오류 메시지를 가져오기 위해 Presentationhost.exe에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7b3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7b3b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7b3b-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="d7b3b-106">제한이 호스트에서 제공 하는 진행률 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="d7b3b-107">제한이 호스트에서 제공 하는 진행률 사용자 인터페이스인 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 클래스의 이름입니다 .를 사용 <xref:System.Windows.Controls.Page> 하는 파일이 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="d7b3b-108">이 클래스는에 지정 `pwzProgressAssemblyName`된 어셈블리에 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="d7b3b-109">제한이 호스트에서 제공한 오류 사용자 인터페이스를 포함 하는 어셈블리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="d7b3b-110">제한이 호스트에서 제공 하는 오류 사용자 인터페이스인 클래스의 이름입니다 .를 사용 <xref:System.Windows.Controls.Page> 하는 XAML 파일은 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="d7b3b-111">이 클래스는에 지정 `pwzErrorAssemblyName`된 어셈블리에 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d7b3b-112">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="d7b3b-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="d7b3b-113">HRESULT: 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7b3b-114">설명</span><span class="sxs-lookup"><span data-stu-id="d7b3b-114">Remarks</span></span>  
 <span data-ttu-id="d7b3b-115">호스트 응용 프로그램에 Presentationhost.exe의 기본 사용자 인터페이스가 준수 하지 않을 수 있는 특정 테마가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="d7b3b-116">이 경우 호스트 응용 프로그램은 [GetCustomUI](getcustomui.md) 를 구현 하 여 진행률 및 오류 사용자 인터페이스를 presentationhost.exe로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="d7b3b-117">Presentationhost.exe는 기본 사용자 인터페이스를 사용 하기 전에 항상 [GetCustomUI](getcustomui.md) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="d7b3b-118">이 함수는 Presentationhost.exe의 초기화 중에 한 번 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7b3b-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b3b-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7b3b-119">See also</span></span>

- [<span data-ttu-id="d7b3b-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="d7b3b-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
