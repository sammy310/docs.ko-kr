---
title: Regsvcs.exe(.NET 서비스 설치 도구)
description: .NET 서비스 설치 도구인 Regsvcs.exe를 사용합니다. 어셈블리를 로드 및 등록하고, 프로그래밍 방식으로 클래스에 추가한 서비스를 구성하는 등의 작업을 수행합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: 03787ecacc00c35f31f1fa5101fff5882e5314f6
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653311"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="e678d-104">Regsvcs.exe(.NET 서비스 설치 도구)</span><span class="sxs-lookup"><span data-stu-id="e678d-104">Regsvcs.exe (.NET Services Installation Tool)</span></span>

<span data-ttu-id="e678d-105">.NET 서비스 설치 도구를 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-105">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="e678d-106">어셈블리를 로드 및 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-106">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="e678d-107">형식 라이브러리를 지정된 COM+ 애플리케이션에 생성, 등록 및 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-107">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="e678d-108">프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-108">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="e678d-109">도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-109">To run the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="e678d-110">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e678d-111">구문</span><span class="sxs-lookup"><span data-stu-id="e678d-111">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="e678d-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e678d-112">Parameters</span></span>  
  
|<span data-ttu-id="e678d-113">인수</span><span class="sxs-lookup"><span data-stu-id="e678d-113">Argument</span></span>|<span data-ttu-id="e678d-114">설명</span><span class="sxs-lookup"><span data-stu-id="e678d-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e678d-115">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="e678d-115">*assemblyFile.dll*</span></span>|<span data-ttu-id="e678d-116">소스 어셈블리 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-116">The source assembly file.</span></span> <span data-ttu-id="e678d-117">강력한 이름으로 어셈블리를 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-117">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="e678d-118">자세한 내용은 [강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e678d-118">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="e678d-119">옵션</span><span class="sxs-lookup"><span data-stu-id="e678d-119">Option</span></span>|<span data-ttu-id="e678d-120">설명</span><span class="sxs-lookup"><span data-stu-id="e678d-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e678d-121">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="e678d-121">**/appdir:** *path*</span></span>|<span data-ttu-id="e678d-122">애플리케이션의 루트 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-122">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="e678d-123">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="e678d-123">**/appname:** *applicationName*</span></span>|<span data-ttu-id="e678d-124">찾거나 만들 COM+ 애플리케이션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-124">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="e678d-125">**/c**</span><span class="sxs-lookup"><span data-stu-id="e678d-125">**/c**</span></span>|<span data-ttu-id="e678d-126">대상 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-126">Creates the target application.</span></span>|  
|<span data-ttu-id="e678d-127">**/componly**</span><span class="sxs-lookup"><span data-stu-id="e678d-127">**/componly**</span></span>|<span data-ttu-id="e678d-128">구성 요소만 구성하고 메서드 및 인터페이스는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-128">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="e678d-129">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="e678d-129">**/exapp**</span></span>|<span data-ttu-id="e678d-130">기존 애플리케이션을 예상하기 위한 도구에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-130">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="e678d-131">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="e678d-131">**/extlb**</span></span>|<span data-ttu-id="e678d-132">기존의 형식 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-132">Uses an existing type library.</span></span>|  
|<span data-ttu-id="e678d-133">**/fc**</span><span class="sxs-lookup"><span data-stu-id="e678d-133">**/fc**</span></span>|<span data-ttu-id="e678d-134">대상 애플리케이션을 찾거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-134">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="e678d-135">**/help**</span><span class="sxs-lookup"><span data-stu-id="e678d-135">**/help**</span></span>|<span data-ttu-id="e678d-136">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-136">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="e678d-137">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="e678d-137">**/noreconfig**</span></span>|<span data-ttu-id="e678d-138">기존의 대상 애플리케이션을 다시 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-138">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="e678d-139">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="e678d-139">**/nologo**</span></span>|<span data-ttu-id="e678d-140">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-140">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="e678d-141">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="e678d-141">**/parname:** *name*</span></span>|<span data-ttu-id="e678d-142">찾거나 만들 COM+ 애플리케이션의 이름 또는 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-142">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="e678d-143">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="e678d-143">**/reconfig**</span></span>|<span data-ttu-id="e678d-144">기존의 대상 애플리케이션을 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-144">Reconfigures an existing target application.</span></span> <span data-ttu-id="e678d-145">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-145">This is the default.</span></span>|  
|<span data-ttu-id="e678d-146">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="e678d-146">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="e678d-147">설치할 형식 라이브러리 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-147">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="e678d-148">**/u**</span><span class="sxs-lookup"><span data-stu-id="e678d-148">**/u**</span></span>|<span data-ttu-id="e678d-149">대상 애플리케이션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-149">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="e678d-150">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="e678d-150">**/quiet**</span></span>|<span data-ttu-id="e678d-151">자동 모드를 지정합니다. 즉, 로고 및 성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-151">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="e678d-152">**/?**</span><span class="sxs-lookup"><span data-stu-id="e678d-152">**/?**</span></span>|<span data-ttu-id="e678d-153">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-153">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e678d-154">설명</span><span class="sxs-lookup"><span data-stu-id="e678d-154">Remarks</span></span>  

 <span data-ttu-id="e678d-155">Regsvcs.exe에는 *assemblyFile.dll* 에서 지정한 소스 어셈블리 파일이 필요하며,</span><span class="sxs-lookup"><span data-stu-id="e678d-155">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="e678d-156">이 어셈블리는 강력한 이름으로 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-156">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="e678d-157">강력한 이름 서명에 대한 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e678d-157">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="e678d-158">대상 애플리케이션 및 형식 라이브러리 파일의 이름은 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-158">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="e678d-159">*applicationName* 인수는 소스 어셈블리 파일에서 생성할 수 있으며, 이 인수가 없는 경우에는 소스 어셈블리 파일에서 생성될 수 있고 Regsvcs.exe로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-159">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="e678d-160">*typelibraryfile* 인수를 사용하여 형식 라이브러리 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-160">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="e678d-161">형식 라이브러리 이름을 지정하지 않으면 해당 어셈블리 이름이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-161">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="e678d-162">Regsvcs.exe는 구성 요소의 메서드를 등록할 때 해당 메서드에 있는 [요청](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) 및 [링크 요청](../misc/link-demands.md)의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-162">When Regsvcs.exe registers a component's methods, it is subject to the [demands](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="e678d-163">이 도구는 완전히 신뢰할 수 있는 환경에서 실행되므로 대부분의 권한 요청이 성공하지만</span><span class="sxs-lookup"><span data-stu-id="e678d-163">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="e678d-164">Regsvcs.exe는 <xref:System.Security.Permissions.StrongNameIdentityPermission> 또는 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대한 요청 또는 링크 요청에 따라 보호된 메서드가 있는 구성 요소를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-164">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="e678d-165">Regsvcs.exe를 사용하려면 로컬 컴퓨터에 대한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-165">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="e678d-166">이러한 작업 수행 도중 오류가 발생하면 해당 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-166">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e678d-167">예</span><span class="sxs-lookup"><span data-stu-id="e678d-167">Examples</span></span>  

 <span data-ttu-id="e678d-168">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 애플리케이션)에 추가하고 `myTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="e678d-169">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 애플리케이션)에 추가하고 `newTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e678d-169">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="e678d-170">참조</span><span class="sxs-lookup"><span data-stu-id="e678d-170">See also</span></span>

- [<span data-ttu-id="e678d-171">도구</span><span class="sxs-lookup"><span data-stu-id="e678d-171">Tools</span></span>](index.md)
- [<span data-ttu-id="e678d-172">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="e678d-172">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="e678d-173">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="e678d-173">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
