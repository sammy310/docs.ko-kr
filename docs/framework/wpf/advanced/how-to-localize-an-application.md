---
title: 앱 지역화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209684"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="b5abd-102">방법: 애플리케이션 지역화</span><span class="sxs-lookup"><span data-stu-id="b5abd-102">How to: Localize an application</span></span>

<span data-ttu-id="b5abd-103">이 자습서에서는 LocBaml 도구를 사용하여 지역화된 애플리케이션을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5abd-104">LocBaml 도구는 프로덕션용 애플리케이션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="b5abd-105">지역화 API 중 일부를 사용하며 지역화 도구를 작성하는 방법을 설명하는 샘플로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="b5abd-106">개요</span><span class="sxs-lookup"><span data-stu-id="b5abd-106">Overview</span></span>

<span data-ttu-id="b5abd-107">이 문서에서는 응용 프로그램을 지역화 하는 단계별 접근 방식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="b5abd-108">먼저 번역할 텍스트를 추출할 수 있도록 응용 프로그램을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="b5abd-109">텍스트를 번역 한 후에는 번역 된 텍스트를 원래 응용 프로그램의 새 복사본으로 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="b5abd-110">샘플 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="b5abd-110">Create a sample application</span></span>

<span data-ttu-id="b5abd-111">이 단계에서는 지역화를 위해 응용 프로그램을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="b5abd-112">Windows Presentation Foundation (WPF) 샘플에서이 토론의 코드 예제에 사용 되는 Helloapp.resources.dll 샘플이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="b5abd-113">이 샘플을 사용 하려면 [LocBaml 도구 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)에서 EXTENSIBLE APPLICATION MARKUP LANGUAGE (XAML) 파일을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5abd-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="b5abd-114">지역화를 시작하려는 지점까지 애플리케이션을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="b5abd-115">MSBuild에서 중립 언어 리소스를 포함 하는 주 어셈블리와 위성 어셈블리 (.dll 확장명이 .resources 인 파일)를 생성 하도록 프로젝트 파일의 개발 언어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="b5abd-116">HelloApp 샘플의 프로젝트 파일은 HelloApp.csproj입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="b5abd-117">해당 파일에서 다음과 같이 식별된 개발 언어를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="b5abd-118">XAML 파일에 Uid를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="b5abd-119">Uid는 파일의 변경 내용을 추적하고 번역해야 하는 항목을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="b5abd-120">파일에 Uid를 추가 하려면 `updateuid` 프로젝트 파일에서를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="b5abd-121">누락 되었거나 중복 된 Uid가 없는지 확인 하려면 다음을 실행 합니다 `checkuid` .</span><span class="sxs-lookup"><span data-stu-id="b5abd-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="b5abd-122">실행 후 `updateuid` 파일에는 uid가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="b5abd-123">예를 들어 Helloapp.resources.dll의 *pane1.xaml* 파일에서 다음을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="b5abd-124">중립 언어 리소스 위성 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="b5abd-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="b5abd-125">응용 프로그램이 중립 언어 리소스 위성 어셈블리를 생성 하도록 구성 된 후 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="b5abd-126">이렇게 하면 기본 응용 프로그램 어셈블리 뿐만 아니라 LocBaml에서 지역화에 필요한 중립 언어 리소스 위성 어셈블리가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="b5abd-127">애플리케이션을 빌드하려면:</span><span class="sxs-lookup"><span data-stu-id="b5abd-127">To build the application:</span></span>  
  
1. <span data-ttu-id="b5abd-128">Helloapp.resources.dll를 컴파일하여 DLL (동적 연결 라이브러리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="b5abd-129">새로 만든 주 응용 프로그램 어셈블리인 Helloapp.resources.dll은 다음 폴더에 만들어집니다. *C:\HelloApp\Bin\Debug*</span><span class="sxs-lookup"><span data-stu-id="b5abd-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="b5abd-130">새로 만든 중립 언어 리소스 위성 어셈블리인 Helloapp.resources.dll은 다음 폴더에 만들어집니다. *C:\HelloApp\Bin\Debug\en-US*</span><span class="sxs-lookup"><span data-stu-id="b5abd-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="b5abd-131">LocBaml 도구 빌드</span><span class="sxs-lookup"><span data-stu-id="b5abd-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="b5abd-132">LocBaml을 빌드하는 데 필요한 모든 파일은 WPF 샘플에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="b5abd-133">[LocBaml 도구 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)에서 c # 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="b5abd-134">명령줄에서 프로젝트 파일(locbaml.csproj)을 실행하여 도구를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="b5abd-135">*Bin\Release* 디렉터리로 이동 하 여 새로 만든 실행 파일 (locbaml)을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="b5abd-136">예: *C:\LocBaml\Bin\Release\locbaml.exe*</span><span class="sxs-lookup"><span data-stu-id="b5abd-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="b5abd-137">LocBaml을 실행할 때 지정할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="b5abd-138">옵션</span><span class="sxs-lookup"><span data-stu-id="b5abd-138">Option</span></span> | <span data-ttu-id="b5abd-139">설명</span><span class="sxs-lookup"><span data-stu-id="b5abd-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="b5abd-140">`parse` 또는 `-p`</span><span class="sxs-lookup"><span data-stu-id="b5abd-140">`parse` or `-p`</span></span> | <span data-ttu-id="b5abd-141">Baml, 리소스 또는 DLL 파일을 구문 분석 하 여 .csv 또는 .txt 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="b5abd-142">`generate` 또는 `-g`</span><span class="sxs-lookup"><span data-stu-id="b5abd-142">`generate` or `-g`</span></span> | <span data-ttu-id="b5abd-143">번역 된 파일을 사용 하 여 지역화 된 이진 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="b5abd-144">`out`또는 `-o` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="b5abd-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="b5abd-145">출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-145">Output file name.</span></span> |
   | <span data-ttu-id="b5abd-146">`culture`또는 `-cul` {*culture*]</span><span class="sxs-lookup"><span data-stu-id="b5abd-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="b5abd-147">출력 어셈블리의 로캘입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="b5abd-148">`translation`또는 `-trans` {*translation .csv*]</span><span class="sxs-lookup"><span data-stu-id="b5abd-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="b5abd-149">번역 또는 지역화 된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="b5abd-150">`asmpath`또는 `-asmpath` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="b5abd-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="b5abd-151">XAML 코드에 사용자 지정 컨트롤이 포함 된 경우 `asmpath` 사용자 지정 컨트롤 어셈블리에를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="b5abd-152"> 로고 또는 저작권 정보를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="b5abd-153"> 자세한 정보 표시 모드 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="b5abd-154">도구를 실행할 때 옵션 목록이 필요한 경우을 입력 `LocBaml.exe` 하 고 enter 키 **를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="b5abd-155">LocBaml을 사용 하 여 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="b5abd-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="b5abd-156">LocBaml 도구를 만들었으므로 이제 이 도구를 통해 HelloApp.resources.dll을 구문 분석하여 지역화할 텍스트 콘텐츠를 추출할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="b5abd-157">주 애플리케이션 어셈블리가 만들어진 애플리케이션의 bin\debug 폴더에 LocBaml.exe를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="b5abd-158">위성 어셈블리 파일을 구문 분석하고 출력을 .csv 파일로 저장하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="b5abd-159">입력 파일 HelloApp.resources.dll이 LocBaml.exe와 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="b5abd-160">LocBaml을 실행하여 파일을 구문 분석하는 경우 출력은 쉼표(.csv 파일) 또는 탭(.txt 파일)으로 구분된 7개 필드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="b5abd-161">다음은 HelloApp.resources.dll에 대해 구문 분석된 .csv 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="b5abd-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="b5abd-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="b5abd-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="b5abd-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="b5abd-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="b5abd-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="b5abd-165">7개 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="b5abd-166">**BAML 이름**.</span><span class="sxs-lookup"><span data-stu-id="b5abd-166">**BAML Name**.</span></span> <span data-ttu-id="b5abd-167">소스 언어 위성 어셈블리와 관련된 BAML 리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="b5abd-168">**리소스 키**입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-168">**Resource Key**.</span></span> <span data-ttu-id="b5abd-169">지역화된 리소스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="b5abd-170">**범주**.</span><span class="sxs-lookup"><span data-stu-id="b5abd-170">**Category**.</span></span> <span data-ttu-id="b5abd-171">값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-171">The value type.</span></span> <span data-ttu-id="b5abd-172">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5abd-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="b5abd-173">**Readability**</span><span class="sxs-lookup"><span data-stu-id="b5abd-173">**Readability**.</span></span> <span data-ttu-id="b5abd-174">로컬라이저가 값을 읽을 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="b5abd-175">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5abd-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="b5abd-176">**Modifiability**</span><span class="sxs-lookup"><span data-stu-id="b5abd-176">**Modifiability**.</span></span> <span data-ttu-id="b5abd-177">로컬라이저가 값을 수정할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="b5abd-178">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5abd-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="b5abd-179">**설명**.</span><span class="sxs-lookup"><span data-stu-id="b5abd-179">**Comments**.</span></span> <span data-ttu-id="b5abd-180">값은 지역화하는 방법을 확인하는 데 도움이 되는 값에 대한 추가 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="b5abd-181">[지역화 특성 및 주석](localization-attributes-and-comments.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b5abd-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="b5abd-182">**값**입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-182">**Value**.</span></span> <span data-ttu-id="b5abd-183">원하는 문화권으로 번역할 텍스트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="b5abd-184">다음 표에서는 이러한 필드가 .csv 파일의 구분된 값에 매핑되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="b5abd-185">BAML 이름</span><span class="sxs-lookup"><span data-stu-id="b5abd-185">BAML name</span></span>|<span data-ttu-id="b5abd-186">리소스 키</span><span class="sxs-lookup"><span data-stu-id="b5abd-186">Resource key</span></span>|<span data-ttu-id="b5abd-187">범주</span><span class="sxs-lookup"><span data-stu-id="b5abd-187">Category</span></span>|<span data-ttu-id="b5abd-188">가독성</span><span class="sxs-lookup"><span data-stu-id="b5abd-188">Readability</span></span>|<span data-ttu-id="b5abd-189">수정 가능성</span><span class="sxs-lookup"><span data-stu-id="b5abd-189">Modifiability</span></span>|<span data-ttu-id="b5abd-190">주석</span><span class="sxs-lookup"><span data-stu-id="b5abd-190">Comments</span></span>|<span data-ttu-id="b5abd-191">Value</span><span class="sxs-lookup"><span data-stu-id="b5abd-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="b5abd-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="b5abd-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="b5abd-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="b5abd-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="b5abd-194">무시</span><span class="sxs-lookup"><span data-stu-id="b5abd-194">Ignore</span></span>|<span data-ttu-id="b5abd-195">FALSE</span><span class="sxs-lookup"><span data-stu-id="b5abd-195">FALSE</span></span>|<span data-ttu-id="b5abd-196">FALSE</span><span class="sxs-lookup"><span data-stu-id="b5abd-196">FALSE</span></span>||<span data-ttu-id="b5abd-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="b5abd-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="b5abd-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="b5abd-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="b5abd-199">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="b5abd-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="b5abd-200">없음</span><span class="sxs-lookup"><span data-stu-id="b5abd-200">None</span></span>|<span data-ttu-id="b5abd-201">TRUE</span><span class="sxs-lookup"><span data-stu-id="b5abd-201">TRUE</span></span>|<span data-ttu-id="b5abd-202">TRUE</span><span class="sxs-lookup"><span data-stu-id="b5abd-202">TRUE</span></span>||<span data-ttu-id="b5abd-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="b5abd-203">Hello World</span></span>|
   |<span data-ttu-id="b5abd-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="b5abd-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="b5abd-205">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="b5abd-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="b5abd-206">없음</span><span class="sxs-lookup"><span data-stu-id="b5abd-206">None</span></span>|<span data-ttu-id="b5abd-207">TRUE</span><span class="sxs-lookup"><span data-stu-id="b5abd-207">TRUE</span></span>|<span data-ttu-id="b5abd-208">TRUE</span><span class="sxs-lookup"><span data-stu-id="b5abd-208">TRUE</span></span>||<span data-ttu-id="b5abd-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="b5abd-209">Goodbye World</span></span>|
  
   <span data-ttu-id="b5abd-210">**설명** 필드의 모든 값에는 값이 포함 되어 있지 않습니다. 필드에 값이 없는 경우 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="b5abd-211">또한 첫 번째 행의 항목은 읽고 수정할 수 없으며 해당 **범주** 값으로 "Ignore"가 있으므로 값을 지역화할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="b5abd-212">구문 분석 된 파일, 특히 많은 파일에서 지역화 가능한 항목의 검색을 용이 하 게 하기 위해 **범주**, **가독성**및 **수정 가능성**을 기준으로 항목을 정렬 하거나 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="b5abd-213">예를 들어 읽을 수 없는 값과 수정할 수 없는 값을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="b5abd-214">지역화할 수 있는 콘텐츠 번역</span><span class="sxs-lookup"><span data-stu-id="b5abd-214">Translate the localizable content</span></span>

<span data-ttu-id="b5abd-215">사용 가능한 임의 도구를 사용하여 추출한 콘텐츠를 번역합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="b5abd-216">이 작업을 수행 하는 좋은 방법은 .csv 파일에 리소스를 기록 하 고 Microsoft Excel에서 확인 하 여 마지막 열 (값)으로 변환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="b5abd-217">LocBaml을 사용 하 여 새 .resources .dll 파일 생성</span><span class="sxs-lookup"><span data-stu-id="b5abd-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="b5abd-218">LocBaml로 HelloApp.resources.dll을 구문 분석하여 식별된 콘텐츠가 번역되었으며 원래 애플리케이션에 다시 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="b5abd-219">`generate`또는 옵션을 사용 `-g` 하 여 새 .resources .dll 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="b5abd-220">다음 구문을 사용하여 새 HelloApp.resources.dll 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="b5abd-221">문화권을 en-US로 표시합니다(/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="b5abd-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="b5abd-222">입력 파일 Hello.csv가 LocBaml.exe 실행 파일과 동일한 디렉터리에 없는 경우 두 파일이 동일한 디렉터리에 있도록 파일 중 하나를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="b5abd-223">*C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* 디렉터리에 있는 이전 *helloapp.resources.dll* 파일을 새로 만든 *helloapp.resources.dll* 파일로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="b5abd-224">이제 애플리케이션에서 "Hello World" 및 "Goodbye World"가 번역됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="b5abd-225">다른 문화권으로 번역하려면 번역할 대상 언어의 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="b5abd-226">다음 예제에서는 프랑스어-캐나다로 번역하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="b5abd-227">주 애플리케이션 어셈블리와 동일한 어셈블리에서 새 위성 어셈블리를 포함할 새 문화권별 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="b5abd-228">프랑스어-캐나다의 경우 폴더는 fr-CA입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="b5abd-229">생성된 위성 어셈블리를 새 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="b5abd-230">새 위성 어셈블리를 테스트하려면 애플리케이션이 실행되는 문화권을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="b5abd-231">이 작업은 다음 두 가지 방법 중 한 가지로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="b5abd-232">운영 체제의 국가별 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="b5abd-233">애플리케이션에서 다음 코드를 App.xaml.cs에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="b5abd-234">LocBaml 사용 팁</span><span class="sxs-lookup"><span data-stu-id="b5abd-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="b5abd-235">사용자 지정 컨트롤을 정의하는 모든 종속 어셈블리를 LocBaml의 로컬 디렉터리에 복사하거나 GAC에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="b5abd-236">이는 지역화 API가 BAML (이진 XAML)을 읽을 때 종속 어셈블리에 액세스할 수 있어야 하기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="b5abd-237">주 어셈블리가 서명된 경우 생성된 리소스 DLL도 서명되어야 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="b5abd-238">지역화된 리소스 DLL 버전을 주 어셈블리와 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abd-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5abd-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5abd-239">See also</span></span>

- [<span data-ttu-id="b5abd-240">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="b5abd-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="b5abd-241">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="b5abd-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
