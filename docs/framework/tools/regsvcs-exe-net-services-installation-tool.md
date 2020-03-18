---
title: Regsvcs.exe(.NET 서비스 설치 도구)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: aecd2f6894558b45898c7f22dd333617d9e2e327
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180356"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="12e6a-102">Regsvcs.exe(.NET 서비스 설치 도구)</span><span class="sxs-lookup"><span data-stu-id="12e6a-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="12e6a-103">.NET 서비스 설치 도구를 사용하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="12e6a-104">어셈블리를 로드 및 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-104">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="12e6a-105">형식 라이브러리를 지정된 COM+ 애플리케이션에 생성, 등록 및 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="12e6a-106">프로그래밍 방식으로 클래스에 추가한 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="12e6a-107">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="12e6a-108">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12e6a-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="12e6a-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e6a-110">구문</span><span class="sxs-lookup"><span data-stu-id="12e6a-110">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="12e6a-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12e6a-111">Parameters</span></span>  
  
|<span data-ttu-id="12e6a-112">인수</span><span class="sxs-lookup"><span data-stu-id="12e6a-112">Argument</span></span>|<span data-ttu-id="12e6a-113">설명</span><span class="sxs-lookup"><span data-stu-id="12e6a-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="12e6a-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="12e6a-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="12e6a-115">소스 어셈블리 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-115">The source assembly file.</span></span> <span data-ttu-id="12e6a-116">강력한 이름으로 어셈블리를 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="12e6a-117">자세한 내용은 [강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12e6a-117">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="12e6a-118">옵션</span><span class="sxs-lookup"><span data-stu-id="12e6a-118">Option</span></span>|<span data-ttu-id="12e6a-119">설명</span><span class="sxs-lookup"><span data-stu-id="12e6a-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="12e6a-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="12e6a-120">**/appdir:** *path*</span></span>|<span data-ttu-id="12e6a-121">애플리케이션의 루트 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="12e6a-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="12e6a-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="12e6a-123">찾거나 만들 COM+ 애플리케이션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="12e6a-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="12e6a-124">**/c**</span></span>|<span data-ttu-id="12e6a-125">대상 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-125">Creates the target application.</span></span>|  
|<span data-ttu-id="12e6a-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="12e6a-126">**/componly**</span></span>|<span data-ttu-id="12e6a-127">구성 요소만 구성하고 메서드 및 인터페이스는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="12e6a-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="12e6a-128">**/exapp**</span></span>|<span data-ttu-id="12e6a-129">기존 애플리케이션을 예상하기 위한 도구에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="12e6a-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="12e6a-130">**/extlb**</span></span>|<span data-ttu-id="12e6a-131">기존의 형식 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="12e6a-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="12e6a-132">**/fc**</span></span>|<span data-ttu-id="12e6a-133">대상 애플리케이션을 찾거나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="12e6a-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="12e6a-134">**/help**</span></span>|<span data-ttu-id="12e6a-135">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="12e6a-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="12e6a-136">**/noreconfig**</span></span>|<span data-ttu-id="12e6a-137">기존의 대상 애플리케이션을 다시 구성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="12e6a-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="12e6a-138">**/nologo**</span></span>|<span data-ttu-id="12e6a-139">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="12e6a-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="12e6a-140">**/parname:** *name*</span></span>|<span data-ttu-id="12e6a-141">찾거나 만들 COM+ 애플리케이션의 이름 또는 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="12e6a-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="12e6a-142">**/reconfig**</span></span>|<span data-ttu-id="12e6a-143">기존의 대상 애플리케이션을 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="12e6a-144">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-144">This is the default.</span></span>|  
|<span data-ttu-id="12e6a-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="12e6a-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="12e6a-146">설치할 형식 라이브러리 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="12e6a-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="12e6a-147">**/u**</span></span>|<span data-ttu-id="12e6a-148">대상 애플리케이션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="12e6a-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="12e6a-149">**/quiet**</span></span>|<span data-ttu-id="12e6a-150">자동 모드를 지정합니다. 즉, 로고 및 성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="12e6a-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="12e6a-151">**/?**</span></span>|<span data-ttu-id="12e6a-152">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12e6a-153">설명</span><span class="sxs-lookup"><span data-stu-id="12e6a-153">Remarks</span></span>  
 <span data-ttu-id="12e6a-154">Regsvcs.exe에는 *assemblyFile.dll*에서 지정한 소스 어셈블리 파일이 필요하며,</span><span class="sxs-lookup"><span data-stu-id="12e6a-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="12e6a-155">이 어셈블리는 강력한 이름으로 서명되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="12e6a-156">강력한 이름 서명에 대한 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12e6a-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="12e6a-157">대상 애플리케이션 및 형식 라이브러리 파일의 이름은 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="12e6a-158">*applicationName* 인수는 소스 어셈블리 파일에서 생성할 수 있으며, 이 인수가 없는 경우에는 소스 어셈블리 파일에서 생성될 수 있고 Regsvcs.exe로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="12e6a-159">*typelibraryfile* 인수를 사용하여 형식 라이브러리 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="12e6a-160">형식 라이브러리 이름을 지정하지 않으면 해당 어셈블리 이름이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="12e6a-161">Regsvcs.exe는 구성 요소의 메서드를 등록할 때 해당 메서드에 있는 [요청](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) 및 [링크 요청](../misc/link-demands.md)의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="12e6a-162">이 도구는 완전히 신뢰할 수 있는 환경에서 실행되므로 대부분의 권한 요청이 성공하지만</span><span class="sxs-lookup"><span data-stu-id="12e6a-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="12e6a-163">Regsvcs.exe는 <xref:System.Security.Permissions.StrongNameIdentityPermission> 또는 <xref:System.Security.Permissions.PublisherIdentityPermission>에 대한 요청 또는 링크 요청에 따라 보호된 메서드가 있는 구성 요소를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="12e6a-164">Regsvcs.exe를 사용하려면 로컬 컴퓨터에 대한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="12e6a-165">이러한 작업 수행 도중 오류가 발생하면 해당 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="12e6a-166">예</span><span class="sxs-lookup"><span data-stu-id="12e6a-166">Examples</span></span>  
 <span data-ttu-id="12e6a-167">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 애플리케이션)에 추가하고 `myTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="12e6a-168">다음 명령을 사용하여 `myTest.dll`에 들어 있는 모든 공용 클래스를 `myTargetApp`(기존의 COM+ 애플리케이션)에 추가하고 `newTest.tlb` 형식 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12e6a-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="12e6a-169">참조</span><span class="sxs-lookup"><span data-stu-id="12e6a-169">See also</span></span>

- [<span data-ttu-id="12e6a-170">도구</span><span class="sxs-lookup"><span data-stu-id="12e6a-170">Tools</span></span>](index.md)
- [<span data-ttu-id="12e6a-171">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="12e6a-171">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="12e6a-172">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="12e6a-172">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
