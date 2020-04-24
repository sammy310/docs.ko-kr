---
title: '방법: 게시자 정책 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646050"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="76849-102">방법: 게시자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="76849-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="76849-103">어셈블리 공급업체는 응용 프로그램이 업그레이드된 어셈블리와 함께 게시자 정책 파일을 포함하여 최신 버전의 어셈블리를 사용해야 한다고 명시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="76849-104">게시자 정책 파일은 어셈블리 리디렉션 및 코드 기본 설정을 지정하고 응용 프로그램 구성 파일과 동일한 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="76849-105">게시자 정책 파일은 어셈블리로 컴파일되어 전역 어셈블리 캐시에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="76849-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="76849-106">게시자 정책을 만드는 데는 세 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="76849-107">게시자 정책 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76849-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="76849-108">게시자 정책 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76849-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="76849-109">전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="76849-110">게시자 정책에 대한 스키마는 [어셈블리 버전 리디렉션에 설명되어 있습니다.](redirect-assembly-versions.md)</span><span class="sxs-lookup"><span data-stu-id="76849-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="76849-111">다음 예제에서는 한 버전을 다른 버전으로 `myAssembly` 리디렉션하는 게시자 정책 파일을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="76849-112">코드 베이스를 지정하는 방법을 알아보려면 [어셈블리의 위치 지정](specify-assembly-location.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="76849-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="76849-113">게시자 정책 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="76849-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="76849-114">[어셈블리 링커(Al.exe)를](../tools/al-exe-assembly-linker.md) 사용하여 게시자 정책 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76849-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="76849-115">게시자 정책 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="76849-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="76849-116">명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="76849-117">이 명령에서 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76849-117">In this command:</span></span>

- <span data-ttu-id="76849-118">인수는 `publisherPolicyFile` 게시자 정책 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76849-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="76849-119">인수는 `publisherPolicyAssemblyFile` 이 명령에서 발생하는 게시자 정책 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76849-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="76849-120">어셈블리 파일 이름은 다음 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="76849-121">'정책.주요번호.마이너넘버.메인어셈블리네임.dll'</span><span class="sxs-lookup"><span data-stu-id="76849-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="76849-122">인수는 `keyPairFile` 키 쌍을 포함하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76849-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="76849-123">동일한 키 쌍을 가진 어셈블리 및 게시자 정책 어셈블리에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="76849-124">인수는 `processorArchitecture` 프로세서 별 어셈블리의 대상 플랫폼을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="76849-125">특정 프로세서 아키텍처를 대상으로 지정하는 기능은 .NET Framework 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="76849-126">특정 프로세서 아키텍처를 대상으로 지정하는 기능은 .NET Framework 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="76849-127">다음 명령은 파일의 키 `policy.1.0.myAssembly` 쌍을 사용하여 어셈블리에 강력한 이름을 할당하고 어셈블리가 x86 프로세서 아키텍처를 대상으로 지정하도록 지정하는 게시자 `pub.config`정책 파일에서 호출된 게시자 정책 어셈블리를 `sgKey.snk` 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76849-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="76849-128">게시자 정책 어셈블리는 적용되는 어셈블리의 프로세서 아키텍처와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="76849-129">따라서 어셈블리에 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> <xref:System.Reflection.ProcessorArchitecture.MSIL>값이 있는 경우 해당 어셈블리에 대한 `/platform:anycpu`게시자 정책 어셈블리를 으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="76849-130">각 프로세서별 어셈블리에 대해 별도의 게시자 정책 어셈블리를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="76849-131">이 규칙의 결과는 어셈블리의 프로세서 아키텍처를 변경하려면 버전 번호의 주 또는 부 구성 요소를 변경하여 올바른 프로세서 아키텍처를 사용하여 새 게시자 정책 어셈블리를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="76849-132">어셈블리에 다른 프로세서 아키텍처가 있으면 이전 게시자 정책 어셈블리가 어셈블리를 서비스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="76849-133">또 다른 결과는 항상 프로세서 아키텍처를 지정하기 때문에 버전 2.0 링커를 사용하여 .NET Framework의 이전 버전을 사용하여 컴파일된 어셈블리에 대한 게시자 정책 어셈블리를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="76849-134">전역 어셈블리 캐시에 게시자 정책 어셈블리 추가</span><span class="sxs-lookup"><span data-stu-id="76849-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="76849-135">전역 [어셈블리 캐시 도구(Gacutil.exe)를](../tools/gacutil-exe-gac-tool.md) 사용하여 전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="76849-136">전역 어셈블리 캐시에 게시자 정책 어셈블리를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="76849-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="76849-137">명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76849-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="76849-138">다음 명령은 `policy.1.0.myAssembly.dll` 전역 어셈블리 캐시에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="76849-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="76849-139">`/link` 인수에 지정된 원래 게시자 정책 파일이 어셈블리와 동일한 디렉터리에 없으면 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76849-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="76849-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76849-140">See also</span></span>

- [<span data-ttu-id="76849-141">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="76849-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="76849-142">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="76849-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="76849-143">구성 파일을 사용하여 앱 구성</span><span class="sxs-lookup"><span data-stu-id="76849-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="76849-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="76849-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="76849-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="76849-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="76849-146">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="76849-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
