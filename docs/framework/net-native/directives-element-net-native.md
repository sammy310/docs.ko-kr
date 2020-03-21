---
title: <Directives>요소(.NET 네이티브)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181052"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="0307a-102">\<지시문> 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="0307a-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="0307a-103">.NET 네이티브에 대한 모든 런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="0307a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0307a-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="0307a-105">특성</span><span class="sxs-lookup"><span data-stu-id="0307a-105">Attributes</span></span>  
  
|<span data-ttu-id="0307a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0307a-106">Attribute</span></span>|<span data-ttu-id="0307a-107">Description</span><span class="sxs-lookup"><span data-stu-id="0307a-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="0307a-108">XML 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-108">The XML namespace.</span></span> <span data-ttu-id="0307a-109">그 값은 항상 **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="0307a-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="0307a-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0307a-110">Child elements</span></span>  
  
|<span data-ttu-id="0307a-111">요소</span><span class="sxs-lookup"><span data-stu-id="0307a-111">Element</span></span>|<span data-ttu-id="0307a-112">Description</span><span class="sxs-lookup"><span data-stu-id="0307a-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0307a-113">\<응용 프로그램></span><span class="sxs-lookup"><span data-stu-id="0307a-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="0307a-114">해당 메타데이터를 리플렉션에 사용할 수 있는 애플리케이션 수준 형식 및 형식 멤버의 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="0307a-115">\<도서관></span><span class="sxs-lookup"><span data-stu-id="0307a-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="0307a-116">런타임에 자식 형식 및 형식 멤버에 메타데이터가 필요한 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0307a-117">설명</span><span class="sxs-lookup"><span data-stu-id="0307a-117">Remarks</span></span>  
 <span data-ttu-id="0307a-118">각 런타임 지시문 파일은 `<Directives>` 요소를 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="0307a-119">요소에는 `<Directives>` [ \<0](application-element-net-native.md) 개 또는 하나 이상의 응용 프로그램>요소와 0, 하나 이상의 [ \<라이브러리>](library-element-net-native.md) 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0307a-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0307a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0307a-120">See also</span></span>

- [<span data-ttu-id="0307a-121">Runtime Directives (rd.xml) Configuration File Reference</span><span class="sxs-lookup"><span data-stu-id="0307a-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="0307a-122">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="0307a-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
