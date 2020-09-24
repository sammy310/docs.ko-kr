---
title: '방법: DEVPATH를 사용하여 어셈블리 찾기'
description: XML 컴퓨터 구성 파일 및 DEVPATH 환경 변수를 사용 하 여 공유 어셈블리가 .NET의 많은 응용 프로그램에서 올바르게 작동 하는지 테스트 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 8ae807e46b11d2adb06d6af0c86e1c7297caa0c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161986"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="d4f7d-103">방법: DEVPATH를 사용하여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="d4f7d-103">How to: Locate Assemblies by Using DEVPATH</span></span>

<span data-ttu-id="d4f7d-104">개발자는 빌드하는 공유 어셈블리가 여러 응용 프로그램에서 올바르게 작동 하는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-104">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="d4f7d-105">개발자는 개발 주기 동안 어셈블리를 전역 어셈블리 캐시에 지속적으로 배치 하는 대신 어셈블리의 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-105">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="d4f7d-106">예를 들어 MySharedAssembly 라는 공유 어셈블리를 빌드하고 출력 디렉터리는 C:\MySharedAssembly\Debug. 라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-106">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="d4f7d-107">C:\MySharedAssembly\Debug를 DEVPATH 변수에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-107">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="d4f7d-108">그런 다음 [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) 컴퓨터 구성 파일에서 요소를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-108">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="d4f7d-109">이 요소는 공용 언어 런타임에 DEVPATH를 사용 하 여 어셈블리를 찾도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-109">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="d4f7d-110">공유 어셈블리는 런타임에서 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-110">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="d4f7d-111">어셈블리 참조를 확인 하기 위한 전용 디렉터리를 지정 하려면 [어셈블리 위치 지정](specify-assembly-location.md)에 설명 된 대로 구성 파일의 [ \<codeBase> 요소](./file-schema/runtime/codebase-element.md) 또는 [ \<probing> 요소](./file-schema/runtime/probing-element.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-111">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="d4f7d-112">응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 배치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-112">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="d4f7d-113">자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-113">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4f7d-114">이는 개발용으로 제공 되는 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-114">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="d4f7d-115">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-115">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f7d-116">예제</span><span class="sxs-lookup"><span data-stu-id="d4f7d-116">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d4f7d-117">이 설정의 기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-117">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4f7d-118">이 설정은 개발 시에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-118">Use this setting only at development time.</span></span> <span data-ttu-id="d4f7d-119">런타임은 DEVPATH에서 찾은 강력한 이름의 어셈블리에 대 한 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-119">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="d4f7d-120">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4f7d-120">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f7d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4f7d-121">See also</span></span>

- [<span data-ttu-id="d4f7d-122">구성 파일을 사용하여 앱 구성</span><span class="sxs-lookup"><span data-stu-id="d4f7d-122">Configuring Apps by using Configuration Files</span></span>](index.md)
