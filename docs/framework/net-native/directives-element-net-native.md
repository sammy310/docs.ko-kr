---
title: <Directives> 요소 (.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128468"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="79abd-102">\<지시문 > 요소 (.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="79abd-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="79abd-103">.NET 네이티브에 대 한 모든 런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="79abd-104">구문</span><span class="sxs-lookup"><span data-stu-id="79abd-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="79abd-105">특성</span><span class="sxs-lookup"><span data-stu-id="79abd-105">Attributes</span></span>  
  
|<span data-ttu-id="79abd-106">특성</span><span class="sxs-lookup"><span data-stu-id="79abd-106">Attribute</span></span>|<span data-ttu-id="79abd-107">설명</span><span class="sxs-lookup"><span data-stu-id="79abd-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="79abd-108">XML 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-108">The XML namespace.</span></span> <span data-ttu-id="79abd-109">해당 값은 항상 **"http://schemas.microsoft.com/netfx/2013/01/metadata"** 입니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="79abd-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="79abd-110">Child elements</span></span>  
  
|<span data-ttu-id="79abd-111">요소</span><span class="sxs-lookup"><span data-stu-id="79abd-111">Element</span></span>|<span data-ttu-id="79abd-112">설명</span><span class="sxs-lookup"><span data-stu-id="79abd-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79abd-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="79abd-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="79abd-114">해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버의 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="79abd-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="79abd-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="79abd-116">런타임에 자식 형식 및 형식 멤버에 메타데이터가 필요한 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79abd-117">주의</span><span class="sxs-lookup"><span data-stu-id="79abd-117">Remarks</span></span>  
 <span data-ttu-id="79abd-118">각 런타임 지시문 파일은 `<Directives>` 요소를 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="79abd-119">`<Directives>` 요소는 [\<Application>](application-element-net-native.md) 요소를 포함하지 않거나 하나 포함할 수 있으며 [\<Library>](library-element-net-native.md) 요소를 포함하지 않거나 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79abd-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79abd-120">참조</span><span class="sxs-lookup"><span data-stu-id="79abd-120">See also</span></span>

- [<span data-ttu-id="79abd-121">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="79abd-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="79abd-122">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="79abd-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
