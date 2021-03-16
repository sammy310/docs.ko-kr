---
title: Lc.exe(라이선스 컴파일러)
description: Lc.exe 즉, 라이선스 컴파일러를 사용합니다. 이 도구는 라이선스 정보를 포함하는 텍스트 파일을 읽고 CLR 실행 파일에 리소스로 포함할 이진 파일을 만듭니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 1a9806cd71f9990d9ce70b35b3af760a22347003
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258805"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="75fe9-104">Lc.exe(라이선스 컴파일러)</span><span class="sxs-lookup"><span data-stu-id="75fe9-104">Lc.exe (License Compiler)</span></span>

<span data-ttu-id="75fe9-105">라이선스 컴파일러를 사용하면 라이선스 정보가 들어 있는 텍스트 파일을 읽고, 공용 언어 런타임 실행 파일에 리소스로 포함될 수 있는 바이너리 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-105">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="75fe9-106">.licx 텍스트 파일은 폼에 라이센스가 있는 컨트롤을 추가할 때마다 Windows Forms 디자이너가 자동으로 생성하고 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-106">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="75fe9-107">컴파일의 일부로 프로젝트 시스템에서는 .licx 텍스트 파일을 .NET 컨트롤 라이선스를 지원하는 .licenses 이진 리소스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-107">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="75fe9-108">그러면 이진 리소스가 프로젝트 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-108">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="75fe9-109">프로젝트를 빌드할 때 라이선스 컴파일러를 사용하면 32비트 및 64비트 간에 크로스 컴파일이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-109">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="75fe9-110">그 이유는 라이선스 컴파일러가 어셈블리를 로드해야 하며 32비트 애플리케이션에서 64비트 어셈블리를 로드하는 것은 허용되지 않으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-110">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="75fe9-111">이 경우 명령줄의 라이선스 컴파일러를 사용하여 라이선스를 수동으로 컴파일하고 해당 아키텍처를 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="75fe9-111">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="75fe9-112">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="75fe9-113">도구를 실행하려면 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-113">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="75fe9-114">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fe9-115">구문</span><span class="sxs-lookup"><span data-stu-id="75fe9-115">Syntax</span></span>  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="75fe9-116">옵션</span><span class="sxs-lookup"><span data-stu-id="75fe9-116">Option</span></span>|<span data-ttu-id="75fe9-117">Description</span><span class="sxs-lookup"><span data-stu-id="75fe9-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="75fe9-118">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="75fe9-118">**/complist:** *filename*</span></span>|<span data-ttu-id="75fe9-119">.licenses 파일에 포함할 라이선스가 있는 구성 요소의 목록이 들어 있는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-119">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="75fe9-120">각 구성 요소는 한 줄에 하나의 구성 요소로 전체 이름을 사용하여 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-120">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="75fe9-121">명령줄 사용자는 프로젝트의 각 형식마다 별도의 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-121">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="75fe9-122">Lc.exe로 여러 개의 입력 파일을 사용하여 하나의 .licenses 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-122">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="75fe9-123">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="75fe9-123">**/h**[**elp**]</span></span>|<span data-ttu-id="75fe9-124">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-124">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="75fe9-125">**/i:** *module*</span><span class="sxs-lookup"><span data-stu-id="75fe9-125">**/i:** *module*</span></span>|<span data-ttu-id="75fe9-126">**/complist** 파일에 나열된 구성 요소가 들어 있는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-126">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="75fe9-127">모듈을 두 개 이상 지정하려면 여러 개의 **/i** 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-127">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="75fe9-128">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="75fe9-128">**/nologo**</span></span>|<span data-ttu-id="75fe9-129">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-129">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="75fe9-130">**/outdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="75fe9-130">**/outdir:** *path*</span></span>|<span data-ttu-id="75fe9-131">출력된 .licenses 파일을 포함할 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-131">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="75fe9-132">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="75fe9-132">**/target:** *targetPE*</span></span>|<span data-ttu-id="75fe9-133">.licenses 파일이 생성되는 대상 실행 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-133">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="75fe9-134">**/v**</span><span class="sxs-lookup"><span data-stu-id="75fe9-134">**/v**</span></span>|<span data-ttu-id="75fe9-135">세부 정보 표시 모드를 지정합니다. 즉, 컴파일 진행 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-135">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="75fe9-136">**@** *file*</span><span class="sxs-lookup"><span data-stu-id="75fe9-136">**@** *file*</span></span>|<span data-ttu-id="75fe9-137">지시 파일(.rsp)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-137">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="75fe9-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="75fe9-138">**/?**</span></span>|<span data-ttu-id="75fe9-139">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75fe9-140">예제</span><span class="sxs-lookup"><span data-stu-id="75fe9-140">Example</span></span>  
  
1. <span data-ttu-id="75fe9-141">`HostApp.exe`라는 애플리케이션의 `Samples.DLL`에 들어 있는 라이선스가 있는 컨트롤 `MyCompany.Samples.LicControl1`을 사용하는 경우 다음 내용이 들어 있는 `HostAppLic.txt`를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-141">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="75fe9-142">다음 명령을 사용하여 `HostApp.exe.licenses`라는 .licenses 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-142">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="75fe9-143">해당 .licenses 파일을 리소스로 포함하는 `HostApp.exe`를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-143">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="75fe9-144">C# 애플리케이션을 빌드하는 경우에는 다음 명령을 사용하여 해당 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-144">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="75fe9-145">다음 명령을 사용하여 `myApp.licenses`, `hostapplic.txt` 및 `hostapplic2.txt`로 지정된, 라이선스가 있는 구성 요소 목록에서 `hostapplic3.txt`를 컴파일하고,</span><span class="sxs-lookup"><span data-stu-id="75fe9-145">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="75fe9-146">`modulesList` 인수를 사용하여 라이선스가 있는 구성 요소가 들어 있는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-146">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="75fe9-147">지시 파일 예</span><span class="sxs-lookup"><span data-stu-id="75fe9-147">Response File Example</span></span>  

 <span data-ttu-id="75fe9-148">다음 목록에서는 지시 파일의 예로 `response.rsp`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-148">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="75fe9-149">지시 파일에 대한 자세한 내용은 [지시 파일](/visualstudio/msbuild/msbuild-response-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75fe9-149">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="75fe9-150">다음 명령줄은 `response.rsp` 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75fe9-150">The following command line uses the `response.rsp` file.</span></span>  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="75fe9-151">참조</span><span class="sxs-lookup"><span data-stu-id="75fe9-151">See also</span></span>

- [<span data-ttu-id="75fe9-152">도구</span><span class="sxs-lookup"><span data-stu-id="75fe9-152">Tools</span></span>](index.md)
- [<span data-ttu-id="75fe9-153">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="75fe9-153">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)
- [<span data-ttu-id="75fe9-154">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="75fe9-154">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
