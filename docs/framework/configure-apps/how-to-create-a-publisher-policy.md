---
title: '방법: 게시자 정책 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: ce2df9d4cea601652ebde2032758137b01faacdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344665"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="779be-102">방법: 게시자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="779be-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="779be-103">어셈블리 공급 업체는 응용 프로그램 업그레이드 된 어셈블리를 사용 하 여 게시자 정책 파일을 포함 하 여 최신 버전의 어셈블리를 사용할지는 상태 수입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="779be-104">게시자 정책 파일 어셈블리 리디렉션 및 코드 베이스 설정을 지정 하 고 응용 프로그램 구성 파일로 동일한 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="779be-105">게시자 정책 파일을 어셈블리로 컴파일되고 전역 어셈블리 캐시에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="779be-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="779be-106">게시자 정책 만들기와 관련 된 세 가지 단계는:</span><span class="sxs-lookup"><span data-stu-id="779be-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1. <span data-ttu-id="779be-107">게시자 정책 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="779be-107">Create a publisher policy file.</span></span>  
  
2. <span data-ttu-id="779be-108">게시자 정책 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="779be-108">Create a publisher policy assembly.</span></span>  
  
3. <span data-ttu-id="779be-109">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="779be-110">게시자 정책에 대 한 스키마에 설명 되어 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="779be-111">다음 예제에서는 게시자 정책 파일 버전으로 리디렉션하는 `myAssembly` 다른 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="779be-112">코드 베이스를 지정 하는 방법에 알아보려면 참조 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="779be-113">게시자 정책 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="779be-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="779be-114">사용 된 [어셈블리 링커 (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) 게시자 정책 어셈블리를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="779be-115">게시자 정책 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="779be-115">To create a publisher policy assembly</span></span>  
  
1. <span data-ttu-id="779be-116">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="779be-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="779be-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="779be-118">이 명령:</span><span class="sxs-lookup"><span data-stu-id="779be-118">In this command:</span></span>  
  
    -   <span data-ttu-id="779be-119">합니다 *publisherPolicyFile* 인수는 게시자 정책 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="779be-120">합니다 *publisherPolicyAssemblyFile* 인수는이 명령에서 발생 하는 게시자 정책 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="779be-121">어셈블리 파일 이름 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="779be-122">**policy.**</span><span class="sxs-lookup"><span data-stu-id="779be-122">**policy.**</span></span> <span data-ttu-id="779be-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="779be-123">*majorNumber* **.**</span></span> <span data-ttu-id="779be-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="779be-124">*minorNumber* **.**</span></span> <span data-ttu-id="779be-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="779be-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="779be-126">합니다 *keyPairFile* 인수는 키 쌍을 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="779be-127">어셈블리와 동일한 키 쌍을 사용 하 여 게시자 정책 어셈블리에 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="779be-128">합니다 *processorArchitecture* 인수 프로세서 특정 어셈블리의 대상 플랫폼을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="779be-129">특정 프로세서 아키텍처를 대상으로 하는 기능은.NET Framework 버전 2.0의에서 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="779be-130">명령을 호출 하는 게시자 정책 어셈블리를 만듭니다 `policy.1.0.myAssembly` 게시자 정책 파일에서 호출 `pub.config`에 있는 키 쌍을 사용 하 여 어셈블리에 강력한 이름을 할당 합니다 `sgKey.snk` 파일과 어셈블리는 x86 대상으로 지정 함을 지정 합니다. 프로세서 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="779be-131">게시자 정책 어셈블리에 적용 되는 어셈블리의 프로세서 아키텍처를 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="779be-132">따라서 어셈블리에 있는 경우는 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> 의 값 <xref:System.Reflection.ProcessorArchitecture.MSIL>를 사용 하 여 해당 어셈블리에 대 한 게시자 정책 어셈블리를 만들어야 합니다 `/platform:anycpu`합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="779be-133">별도 변경 하면 각 프로세서 특정 어셈블리에 대 한 게시자 정책 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="779be-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="779be-134">이 규칙에 따른은 어셈블리의 프로세서 아키텍처를 변경 하기 위해 버전 번호의 주 또는 부 버전 구성 요소 변경 해야 하므로 올바른 프로세서 아키텍처를 사용 하는 새 게시자 정책 어셈블리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="779be-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="779be-135">어셈블리에는 다른 프로세서 아키텍처 이전 게시자 정책 어셈블리에서 어셈블리를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="779be-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="779be-136">다른 결과 항상 프로세서 아키텍처를 지정 하기 때문에 이전 버전의.NET Framework를 사용 하 여 컴파일된 어셈블리에 대 한 게시자 정책 어셈블리를 만드는 버전 2.0 링커를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="779be-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="779be-137">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가</span><span class="sxs-lookup"><span data-stu-id="779be-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="779be-138">사용 된 [전역 어셈블리 캐시 도구 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="779be-139">게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="779be-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1. <span data-ttu-id="779be-140">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="779be-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="779be-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="779be-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="779be-142">다음 명령을 추가 `policy.1.0.myAssembly.dll` 전역 어셈블리 캐시에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="779be-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="779be-143">원래 게시자 정책 파일이 어셈블리와 동일한 디렉터리에 위치한 하지 않는 한 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="779be-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="779be-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="779be-144">See also</span></span>

- [<span data-ttu-id="779be-145">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="779be-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="779be-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="779be-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="779be-147">구성 파일을 사용 하 여 앱 구성</span><span class="sxs-lookup"><span data-stu-id="779be-147">Configuring Apps by using Configuration Files</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="779be-148">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="779be-148">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="779be-149">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="779be-149">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="779be-150">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="779be-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
