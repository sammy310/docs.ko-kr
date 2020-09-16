---
title: .NET Framework 도구
description: .NET을 대상으로 하는 애플리케이션 및 구성 요소를 더 쉽게 만들고 배포하고 관리할 수 있게 해주는 .NET 도구 목록을 확인하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
ms.openlocfilehash: 96df5a0c8487d3ba344b3aa13ca74b92e428d5aa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556683"
---
# <a name="net-framework-tools"></a><span data-ttu-id="63119-103">.NET Framework 도구</span><span class="sxs-lookup"><span data-stu-id="63119-103">.NET Framework Tools</span></span>

<span data-ttu-id="63119-104">.NET Framework 도구를 사용하면 .NET Framework를 대상으로 하는 애플리케이션 및 구성 요소를 보다 쉽게 만들고 배포하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-104">The .NET Framework tools make it easier for you to create, deploy, and manage applications and components that target the .NET Framework.</span></span>

<span data-ttu-id="63119-105">이 단원에서 설명하는 대부분의 .NET Framework 도구는 Visual Studio와 함께 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="63119-105">Most of the .NET Framework tools described in this section are automatically installed with Visual Studio.</span></span> <span data-ttu-id="63119-106">Visual Studio를 다운로드하려면 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 페이지를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="63119-106">To download Visual Studio, visit the [Visual Studio Downloads](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) page.</span></span>

<span data-ttu-id="63119-107">어셈블리 캐시 뷰어(*Shfusion.dll*)를 제외한 모든 도구는 명령줄에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-107">You can run all the tools from the command line with the exception of the Assembly Cache Viewer (*Shfusion.dll*).</span></span> <span data-ttu-id="63119-108">*Shfusion.dll*에 액세스하려면 파일 탐색기를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-108">You must access *Shfusion.dll* from File Explorer.</span></span>
  
<span data-ttu-id="63119-109">명령줄 도구를 실행하는 가장 좋은 방법은 Visual Studio의 개발자 명령 프롬프트를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="63119-109">The best way to run the command-line tools is by using the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="63119-110">이러한 유틸리티를 사용하면 설치 폴더로 이동하지 않아도 도구를 쉽게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-110">These utilities enable you to run the tools easily, without navigating to the installation folder.</span></span> <span data-ttu-id="63119-111">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63119-111">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="63119-112">일부 도구는 32비트 컴퓨터 또는 64비트 컴퓨터 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="63119-112">Some tools are specific to either 32-bit computers or 64-bit computers.</span></span> <span data-ttu-id="63119-113">컴퓨터에 적절한 버전의 도구를 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="63119-113">Be sure to run the appropriate version of the tool for your computer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="63119-114">단원 내용</span><span class="sxs-lookup"><span data-stu-id="63119-114">In this section</span></span>

- [<span data-ttu-id="63119-115">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="63119-115">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)  
<span data-ttu-id="63119-116">모듈 또는 리소스 파일로부터 어셈블리 매니페스트가 있는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-116">Generates a file that has an assembly manifest from modules or resource files.</span></span>

- [<span data-ttu-id="63119-117">Aximp.exe(Windows Forms ActiveX 컨트롤 가져오기)</span><span class="sxs-lookup"><span data-stu-id="63119-117">Aximp.exe (Windows Forms ActiveX Control Importer)</span></span>](aximp-exe-windows-forms-activex-control-importer.md)  
<span data-ttu-id="63119-118">ActiveX 컨트롤용 COM 형식 라이브러리의 형식 정의를 Windows Forms 컨트롤로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-118">Converts type definitions in a COM type library for an ActiveX control into a Windows Forms control.</span></span>

- [<span data-ttu-id="63119-119">Caspol.exe(코드 액세스 보안 정책 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-119">Caspol.exe (Code Access Security Policy Tool)</span></span>](caspol-exe-code-access-security-policy-tool.md)  
<span data-ttu-id="63119-120">컴퓨터 정책 수준, 사용자 정책 수준 및 엔터프라이즈 정책 수준의 보안 정책을 보고 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-120">Enables you to view and configure security policy for the machine policy level, the user policy level, and the enterprise policy level.</span></span> <span data-ttu-id="63119-121">.NET Framework 4 이상에서 [\<legacyCasPolicy> 요소](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)를 `true`로 설정하지 않으면 이 도구는 CAS(코드 액세스 보안) 정책에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-121">In the .NET Framework 4 and later, this tool does not affect code access security (CAS) policy unless the [\<legacyCasPolicy> element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) is set to `true`.</span></span> <span data-ttu-id="63119-122">자세한 내용은 [보안 변경 내용](/previous-versions/dotnet/framework/security/security-changes)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63119-122">For more information, see [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>

- [<span data-ttu-id="63119-123">Cert2spc.exe(SPC 테스트 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-123">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>](cert2spc-exe-software-publisher-certificate-test-tool.md)  
<span data-ttu-id="63119-124">하나 이상의 X.509 인증서에서 SPC(소프트웨어 게시 인증서)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63119-124">Creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="63119-125">이 도구는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="63119-125">This tool is for testing purposes only.</span></span>

- [<span data-ttu-id="63119-126">Certmgr.exe(인증서 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-126">Certmgr.exe (Certificate Manager Tool)</span></span>](certmgr-exe-certificate-manager-tool.md)  
<span data-ttu-id="63119-127">인증서, CTL(인증서 신뢰 목록) 및 CRL(인증서 해지 목록)을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-127">Manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>

- [<span data-ttu-id="63119-128">Clrver.exe(CLR 버전 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-128">Clrver.exe (CLR Version Tool)</span></span>](clrver-exe-clr-version-tool.md)  
<span data-ttu-id="63119-129">컴퓨터에서 CLR(공용 언어 런타임)의 모든 설치 버전을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-129">Reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>

- [<span data-ttu-id="63119-130">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="63119-130">Command Prompts</span></span>](developer-command-prompt-for-vs.md)  
<span data-ttu-id="63119-131">.NET Framework 도구를 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-131">Enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="63119-132">이는 특정 환경 변수를 자동으로 설정하는 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="63119-132">It is a command prompt that automatically sets specific environment variables.</span></span>

- [<span data-ttu-id="63119-133">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-133">CorFlags.exe (CorFlags Conversion Tool)</span></span>](corflags-exe-corflags-conversion-tool.md)  
<span data-ttu-id="63119-134">PE(이식 가능한 실행) 이미지 헤더의 CorFlags 섹션을 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-134">Lets you configure the CorFlags section of the header of a portable executable (PE) image.</span></span>

- [<span data-ttu-id="63119-135">Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)</span><span class="sxs-lookup"><span data-stu-id="63119-135">Fuslogvw.exe (Assembly Binding Log Viewer)</span></span>](fuslogvw-exe-assembly-binding-log-viewer.md)  
<span data-ttu-id="63119-136">.NET Framework에서 런타임에 어셈블리를 찾지 못하는 이유를 진단하는 데 도움이 되는 어셈블리 바인딩에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-136">Displays information about assembly binds to help you diagnose why the .NET Framework cannot locate an assembly at run time.</span></span>

- [<span data-ttu-id="63119-137">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-137">Gacutil.exe (Global Assembly Cache Tool)</span></span>](gacutil-exe-gac-tool.md)  
<span data-ttu-id="63119-138">전역 어셈블리 캐시와 다운로드 캐시의 내용을 보거나 조작할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-138">Lets you view and manipulate the contents of the global assembly cache and download cache.</span></span>

- [<span data-ttu-id="63119-139">Ilasm.exe(IL 어셈블러)</span><span class="sxs-lookup"><span data-stu-id="63119-139">Ilasm.exe (IL Assembler)</span></span>](ilasm-exe-il-assembler.md)  
<span data-ttu-id="63119-140">IL(Intermediate Language)로 PE(이식 가능한 실행) 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-140">Generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="63119-141">이렇게 생성된 실행 파일을 실행하여 IL이 예상대로 실행되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-141">You can run the resulting executable to determine whether the IL performs as expected.</span></span>

- [<span data-ttu-id="63119-142">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="63119-142">Ildasm.exe (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)  
<span data-ttu-id="63119-143">IL(Intermediate Language) 코드가 들어 있는 PE(이식 가능한 실행) 파일을 사용하여 IL 어셈블러(Ilasm.exe)에 입력할 수 있는 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63119-143">Takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file that can be input to the IL Assembler (Ilasm.exe).</span></span>

- [<span data-ttu-id="63119-144">Installutil.exe(설치 관리자 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-144">Installutil.exe (Installer Tool)</span></span>](installutil-exe-installer-tool.md)  
<span data-ttu-id="63119-145">특정 어셈블리에서 설치 관리자 구성 요소를 실행하는 방법으로 서버 리소스를 설치하고 제거할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-145">Enables you to install and uninstall server resources by executing the installer components in a specified assembly.</span></span> <span data-ttu-id="63119-146"><xref:System.Configuration.Install> 네임스페이스의 클래스에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-146">(Works with classes in the <xref:System.Configuration.Install> namespace.)</span></span>

- [<span data-ttu-id="63119-147">Lc.exe(라이선스 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="63119-147">Lc.exe (License Compiler)</span></span>](lc-exe-license-compiler.md)  
<span data-ttu-id="63119-148">라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함할 수 있는 *.licenses* 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-148">Reads text files that contain licensing information and produces a *.licenses* file that can be embedded in a common language runtime executable as a resource.</span></span>

- [<span data-ttu-id="63119-149">Mage.exe(매니페스트 생성 및 편집 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-149">Mage.exe (Manifest Generation and Editing Tool)</span></span>](mage-exe-manifest-generation-and-editing-tool.md)  
<span data-ttu-id="63119-150">애플리케이션 및 배포 매니페스트를 만들고, 편집하고, 서명할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-150">Lets you create, edit, and sign application and deployment manifests.</span></span> <span data-ttu-id="63119-151">*Mage.exe*는 명령줄 도구로서 일괄 처리 스크립트뿐 아니라 ASP.NET 애플리케이션을 비롯한 Windows 기반 애플리케이션에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-151">As a command-line tool, *Mage.exe* can be run from both batch scripts and other Windows-based applications, including ASP.NET applications.</span></span>

- [<span data-ttu-id="63119-152">MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)</span><span class="sxs-lookup"><span data-stu-id="63119-152">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
<span data-ttu-id="63119-153">명령줄 도구인 Mage.exe와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-153">Supports the same functionality as the command-line tool Mage.exe, but uses a Windows-based user interface (UI).</span></span> <span data-ttu-id="63119-154">명령줄 도구인 *Mage.exe*와 동일한 기능을 지원하지만 Windows 기반 UI(사용자 인터페이스)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-154">Supports the same functionality as the command-line tool *Mage.exe*, but uses a Windows-based user interface (UI).</span></span>

- [<span data-ttu-id="63119-155">MDbg.exe(.NET Framework 명령줄 디버거)</span><span class="sxs-lookup"><span data-stu-id="63119-155">MDbg.exe (.NET Framework Command-Line Debugger)</span></span>](mdbg-exe.md)  
<span data-ttu-id="63119-156">도구 공급업체 및 애플리케이션 개발자가 .NET Framework 공용 언어 런타임을 대상으로 하는 프로그램에서 버그를 쉽게 찾아서 수정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="63119-156">Helps tools vendors and application developers find and fix bugs in programs that target the .NET Framework common language runtime.</span></span> <span data-ttu-id="63119-157">이 도구에는 디버깅 서비스를 제공하기 위해 런타임 디버깅 API가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="63119-157">This tool uses the runtime debugging API to provide debugging services.</span></span>

- [<span data-ttu-id="63119-158">Mgmtclassgen.exe(강력하게 형식화된 관리 클래스 생성기)</span><span class="sxs-lookup"><span data-stu-id="63119-158">Mgmtclassgen.exe (Management Strongly Typed Class Generator)</span></span>](mgmtclassgen-exe.md)  
<span data-ttu-id="63119-159">지정된 WMI(Windows Management Instrumentation) 클래스에 대한 초기 바인딩 관리되는 클래스를 생성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-159">Enables you to generate an early-bound managed class for a specified Windows Management Instrumentation (WMI) class.</span></span>

- [<span data-ttu-id="63119-160">Mpgo.exe(관리되는 프로필 기반 최적화 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-160">Mpgo.exe (Managed Profile Guided Optimization Tool)</span></span>](mpgo-exe-managed-profile-guided-optimization-tool.md)  
<span data-ttu-id="63119-161">일반 최종 사용자 시나리오를 사용하여 네이티브 이미지 어셈블리를 조정하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-161">Enables you to tune native image assemblies using common end-user scenarios.</span></span> <span data-ttu-id="63119-162">Mpgo.exe는 애플리케이션 개발자가 선택한 교육 시나리오를 사용하여 네이티브 이미지 애플리케이션 어셈블리(.NET Framework 어셈블리는 아님)에 대한 프로필 데이터를 생성하고 사용할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-162">Mpgo.exe allows the generation and consumption of profile data for native image application assemblies (not the .NET Framework assemblies) using training scenarios selected by the application developer.</span></span>

- [<span data-ttu-id="63119-163">Ngen.exe(네이티브 이미지 생성기)</span><span class="sxs-lookup"><span data-stu-id="63119-163">Ngen.exe (Native Image Generator)</span></span>](ngen-exe-native-image-generator.md)  
<span data-ttu-id="63119-164">컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 사용하여 관리되는 애플리케이션의 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="63119-164">Improves the performance of managed applications through the use of native images (files containing compiled processor-specific machine code).</span></span> <span data-ttu-id="63119-165">런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-165">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

- [<span data-ttu-id="63119-166">Peverify.exe(PEVerify 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-166">Peverify.exe (PEVerify Tool)</span></span>](peverify-exe-peverify-tool.md)  
<span data-ttu-id="63119-167">MSIL(Microsoft Intermediate Language) 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 여부를 쉽게 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-167">Helps you verify whether your Microsoft intermediate language (MSIL) code and associated metadata meet type safety requirements.</span></span>

- [<span data-ttu-id="63119-168">Regasm.exe(어셈블리 등록 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-168">Regasm.exe (Assembly Registration Tool)</span></span>](regasm-exe-assembly-registration-tool.md)  
<span data-ttu-id="63119-169">어셈블리 내의 메타데이터를 읽고 레지스트리에 필요한 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-169">Reads the metadata within an assembly and adds the necessary entries to the registry.</span></span> <span data-ttu-id="63119-170">이렇게 하면 COM 클라이언트를 .NET Framework 클래스로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-170">This enables COM clients to appear as .NET Framework classes.</span></span>

- [<span data-ttu-id="63119-171">Regsvcs.exe(.NET 서비스 설치 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-171">Regsvcs.exe (.NET Services Installation Tool)</span></span>](regsvcs-exe-net-services-installation-tool.md)  
<span data-ttu-id="63119-172">어셈블리를 로드 및 등록하고, 형식 라이브러리를 생성하여 지정된 COM+ 버전 1.0 애플리케이션에 설치하며, 프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-172">Loads and registers an assembly, generates and installs a type library into a specified COM+ version 1.0 application, and configures services that you have added programmatically to a class.</span></span>

- [<span data-ttu-id="63119-173">Resgen.exe(리소스 파일 생성기)</span><span class="sxs-lookup"><span data-stu-id="63119-173">Resgen.exe (Resource File Generator)</span></span>](resgen-exe-resource-file-generator.md)  
<span data-ttu-id="63119-174">텍스트 파일( *.txt* 또는 *.restext*)과 XML 기반 리소스 형식 파일( *.resx*)을 런타임 이진 실행 파일에 포함하거나 위성 어셈블리로 컴파일할 수 있는 공용 언어 런타임 이진 파일( *.resources*)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-174">Converts text (*.txt* or *.restext*) files and XML-based resource format (*.resx*) files to common language runtime binary (*.resources*) files that can be embedded in a runtime binary executable or compiled into satellite assemblies.</span></span>

- [<span data-ttu-id="63119-175">SecAnnotate.exe(.NET Security Annotator 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-175">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>](secannotate-exe-net-security-annotator-tool.md)  
<span data-ttu-id="63119-176">어셈블리의 `SecurityCritical` 및 `SecuritySafeCritical` 부분을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-176">Identifies the `SecurityCritical` and `SecuritySafeCritical` portions of an assembly.</span></span>

- [<span data-ttu-id="63119-177">SignTool.exe(서명 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-177">SignTool.exe (Sign Tool)</span></span>](signtool-exe.md)  
<span data-ttu-id="63119-178">파일에 디지털 서명을 하고, 파일의 서명을 확인하고, 파일에 타임스탬프를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-178">Digitally signs files, verifies signatures in files, and time-stamps files.</span></span>

- [<span data-ttu-id="63119-179">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-179">Sn.exe (Strong Name Tool)</span></span>](sn-exe-strong-name-tool.md)  
<span data-ttu-id="63119-180">강력한 이름을 사용하여 어셈블리를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-180">Helps create assemblies with strong names.</span></span> <span data-ttu-id="63119-181">이 도구는 키 관리, 서명 생성 및 서명 확인을 위한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-181">This tool provides options for key management, signature generation, and signature verification.</span></span>

- [<span data-ttu-id="63119-182">SOS.dll(SOS 디버깅 확장)</span><span class="sxs-lookup"><span data-stu-id="63119-182">SOS.dll (SOS Debugging Extension)</span></span>](sos-dll-sos-debugging-extension.md)  
<span data-ttu-id="63119-183">내부 공용 언어 런타임 환경에 대한 정보를 제공하여 관리되는 프로그램을 WinDbg.exe 디버거와 Visual Studio에서 쉽게 디버깅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-183">Helps you debug managed programs in the WinDbg.exe debugger and in Visual Studio by providing information about the internal common language runtime environment.</span></span>

- [<span data-ttu-id="63119-184">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-184">SqlMetal.exe (Code Generation Tool)</span></span>](sqlmetal-exe-code-generation-tool.md)  
<span data-ttu-id="63119-185">.NET Framework의 LINQ to SQL 구성 요소에 대한 코드와 매핑을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-185">Generates code and mapping for the LINQ to SQL component of the .NET Framework.</span></span>

- [<span data-ttu-id="63119-186">Storeadm.exe(격리된 스토리지 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-186">Storeadm.exe (Isolated Storage Tool)</span></span>](storeadm-exe-isolated-storage-tool.md)  
<span data-ttu-id="63119-187">사용자의 저장소를 나열하고 삭제할 수 있는 옵션을 제공함으로써 격리된 스토리지를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-187">Manages isolated storage; provides options for listing the user's stores and deleting them.</span></span>

- [<span data-ttu-id="63119-188">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="63119-188">Tlbexp.exe (Type Library Exporter)</span></span>](tlbexp-exe-type-library-exporter.md)  
<span data-ttu-id="63119-189">공용 언어 런타임 어셈블리에 정의된 형식을 설명하는 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-189">Generates a type library that describes the types that are defined in a common language runtime assembly.</span></span>

- [<span data-ttu-id="63119-190">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="63119-190">Tlbimp.exe (Type Library Importer)</span></span>](tlbimp-exe-type-library-importer.md)  
<span data-ttu-id="63119-191">COM 형식 라이브러리에 있는 형식 정의를 공용 언어 런타임 어셈블리에 있는 동일한 기능의 정의로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-191">Converts the type definitions found in a COM type library into equivalent definitions in a common language runtime assembly.</span></span>

- [<span data-ttu-id="63119-192">Winmdexp.exe(Windows 런타임 메타데이터 내보내기 도구)</span><span class="sxs-lookup"><span data-stu-id="63119-192">Winmdexp.exe (Windows Runtime Metadata Export Tool)</span></span>](winmdexp-exe-windows-runtime-metadata-export-tool.md)  
<span data-ttu-id="63119-193">*.winmdobj* 파일로 컴파일된 .NET Framework 어셈블리를 Windows 런타임 메타데이터 및 구현 정보가 둘 다 포함된 *.winmd* 파일로 패키지된 Windows 런타임 구성 요소에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="63119-193">Exports a .NET Framework assembly that is compiled as a *.winmdobj* file into a Windows Runtime component, which is packaged as a *.winmd* file that contains both Windows Runtime metadata and implementation information.</span></span>

- [<span data-ttu-id="63119-194">Winres.exe(Windows Forms 리소스 편집기)</span><span class="sxs-lookup"><span data-stu-id="63119-194">Winres.exe (Windows Forms Resource Editor)</span></span>](winres-exe-windows-forms-resource-editor.md)  
<span data-ttu-id="63119-195">Windows Forms에 사용되는 UI(사용자 인터페이스) 리소스( *.resx* 또는 *.resources* 파일)를 쉽게 지역화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63119-195">Helps you localize user interface (UI) resources (*.resx* or *.resources* files) that are used by Windows Forms.</span></span> <span data-ttu-id="63119-196">문자열을 번역한 다음 지역화(번역)된 문자열에 적합하도록 컨트롤의 크기를 조정하거나 컨트롤을 이동하고 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-196">You can translate strings, and then size, move, and hide controls to accommodate the localized strings.</span></span>

## <a name="related-sections"></a><span data-ttu-id="63119-197">관련 단원</span><span class="sxs-lookup"><span data-stu-id="63119-197">Related sections</span></span>

- <span data-ttu-id="63119-198">[WPF 도구](/previous-versions/ms742404(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="63119-198">[WPF Tools](/previous-versions/ms742404(v=vs.110))</span></span>  
<span data-ttu-id="63119-199">isXPS 규칙 도구(isXPS.exe) 및 성능 프로파일링 도구와 같은 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-199">Includes tools such as the isXPS Conformance tool (isXPS.exe) and performance profiling tools.</span></span>

- [<span data-ttu-id="63119-200">Windows Communication Foundation 도구</span><span class="sxs-lookup"><span data-stu-id="63119-200">Windows Communication Foundation Tools</span></span>](../wcf/tools.md)  
<span data-ttu-id="63119-201">WCF(Windows Communication Foundation) 애플리케이션을 보다 쉽게 만들고 배포하고 관리할 수 있도록 지원하는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63119-201">Includes tools that make it easier for you to create, deploy, and manage Windows Communication Foundation (WCF) applications.</span></span>
