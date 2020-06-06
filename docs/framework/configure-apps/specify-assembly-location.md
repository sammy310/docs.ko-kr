---
title: 어셈블리 위치 지정
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "81646027"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="181bf-102">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="181bf-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="181bf-103">어셈블리 위치를 지정 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="181bf-104">요소를 사용 [\<codeBase>](./file-schema/runtime/codebase-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="181bf-105">요소를 사용 [\<probing>](./file-schema/runtime/probing-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="181bf-106">또한 [.NET Framework 구성 도구 (mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) 를 사용 하 여 어셈블리 위치를 지정 하거나 어셈블리를 검색할 공용 언어 런타임에 대 한 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="181bf-107">요소 사용 \<codeBase></span><span class="sxs-lookup"><span data-stu-id="181bf-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="181bf-108">**\<codeBase>** 요소는 어셈블리 버전을 리디렉션하는 컴퓨터 구성 또는 게시자 정책 파일 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="181bf-109">런타임에서 사용할 어셈블리 버전을 결정 하면 버전을 결정 하는 파일의 코드 베이스 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="181bf-110">코드 베이스가 표시 되지 않는 경우 런타임은 일반적인 방법으로 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="181bf-111">자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="181bf-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="181bf-112">다음 예제에서는 어셈블리의 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="181bf-113">**Version** 특성은 강력한 이름의 어셈블리에 필요 하지만 강력한 이름이 아닌 어셈블리의 경우 생략 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="181bf-114">**\<codeBase>** 요소에 **href** 특성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="181bf-115">요소에는 버전 범위를 지정할 수 없습니다 **\<codeBase>** .</span><span class="sxs-lookup"><span data-stu-id="181bf-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="181bf-116">강력한 이름의 어셈블리에 대 한 코드 베이스 힌트를 제공 하는 경우 힌트는 응용 프로그램 기본 디렉터리의 하위 디렉터리 또는 응용 프로그램을 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="181bf-117">요소 사용 \<probing></span><span class="sxs-lookup"><span data-stu-id="181bf-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="181bf-118">런타임은 코드 베이스가 없는 어셈블리를 검색 하 여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="181bf-119">검색에 대 한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="181bf-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="181bf-120">[\<probing>](./file-schema/runtime/probing-element.md)응용 프로그램 구성 파일의 요소를 사용 하 여 런타임이 어셈블리를 찾을 때 검색 해야 하는 하위 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="181bf-121">다음 예제에서는 런타임에서 검색할 디렉터리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="181bf-122">**PrivatePath** 특성은 런타임에서 어셈블리를 검색 해야 하는 디렉터리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="181bf-123">응용 프로그램이 C:\Program 런타임에 files\myapp에 있는 경우 런타임은 C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin 및 C:\Program Files\MyApp\Bin3.에서 코드 베이스를 지정 하지 않는 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="181bf-124">**PrivatePath** 에 지정 된 디렉터리는 응용 프로그램 기본 디렉터리의 하위 디렉터리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="181bf-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181bf-125">참조</span><span class="sxs-lookup"><span data-stu-id="181bf-125">See also</span></span>

- [<span data-ttu-id="181bf-126">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="181bf-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="181bf-127">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="181bf-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="181bf-128">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="181bf-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="181bf-129">구성 파일을 사용하여 앱 구성</span><span class="sxs-lookup"><span data-stu-id="181bf-129">Configuring Apps by using Configuration Files</span></span>](index.md)
