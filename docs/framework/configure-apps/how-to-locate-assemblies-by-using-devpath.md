---
title: '방법: DEVPATH를 사용하여 어셈블리 찾기'
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 5c4041f42b0a9d1d1e4bc8438e662911534daa42
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775832"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="78f90-102">방법: DEVPATH를 사용하여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="78f90-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="78f90-103">개발자가 작성 하는 공유 어셈블리를 여러 응용 프로그램을 사용 하 여 올바르게 작동 하는지 확인 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="78f90-104">지속적으로 어셈블리를 전역 어셈블리 캐시에서 개발 주기 동안에 배치 하는 대신 개발자는 어셈블리에 대 한 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="78f90-105">출력 디렉터리는 C:\MySharedAssembly\Debug 고 예를 들어 MySharedAssembly 라는 공유 어셈블리를 작성할 수 있도록를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="78f90-106">C:\MySharedAssembly\Debug DEVPATH 변수에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="78f90-107">지정 해야 합니다 [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) 컴퓨터 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="78f90-108">이 요소에는 공용 언어 런타임을 어셈블리를 찾는 데 DEVPATH를 사용 하도록 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="78f90-109">공유 어셈블리는 런타임에서 검색할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="78f90-110">어셈블리 참조 사용을 확인 하기 위한 전용 디렉터리를 지정 하는 [ \<코드 베이스 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 하거나 [ \<검색 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 에 설명 된 대로 구성 파일에서 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="78f90-111">또한 응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="78f90-112">자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78f90-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78f90-113">이것이 개발만을 위한 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="78f90-114">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78f90-115">예제</span><span class="sxs-lookup"><span data-stu-id="78f90-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="78f90-116">이 설정의 기본값은 false입니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78f90-117">개발 타임에만이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-117">Use this setting only at development time.</span></span> <span data-ttu-id="78f90-118">런타임에서 DEVPATH에 있는 강력한 이름의 어셈블리의 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="78f90-119">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78f90-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f90-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="78f90-120">See also</span></span>

- [<span data-ttu-id="78f90-121">구성 파일을 사용 하 여 앱 구성</span><span class="sxs-lookup"><span data-stu-id="78f90-121">Configuring Apps by using Configuration Files</span></span>](index.md)
