---
title: Visual Studio용 개발자 명령 프롬프트
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59af252967a18eca858035fb0a3465d909734ddf
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71044736"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="12a82-102">Visual Studio용 개발자 명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="12a82-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="12a82-103">Visual Studio에 대한 개발자 명령 프롬프트를 통해 .NET Framework 도구를 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="12a82-104">이는 특정 환경 변수를 자동으로 설정하는 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="12a82-105">Visual Studio 다운로드</span><span class="sxs-lookup"><span data-stu-id="12a82-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="12a82-106">머신에서 명령 프롬프트 검색</span><span class="sxs-lookup"><span data-stu-id="12a82-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="12a82-107">설치한 Visual Studio의 버전과 추가 SDK에 따라 여러 개의 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="12a82-108">예를 들어 64비트 버전의 Visual Studio는 32비트 및 64비트 명령 프롬프트를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="12a82-109">(32비트 및 64비트 버전의 도구는 대부분 동일하지만, 몇 가지 도구는 32비트 및 64비트 환경에 맞게 변경됩니다.) 다음 단계가 작동하지 않는 경우 [머신에서 수동으로 파일 찾기](#manually-locate-the-files-on-your-machine) 또는 [Visual Studio 내에서 명령 프롬프트 실행](#run-the-command-prompt-from-inside-visual-studio)을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="12a82-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="12a82-110">In Windows 10</span></span>

1. <span data-ttu-id="12a82-111">작업 표시줄의 검색 상자에 `dev` 또는 `developer command prompt`와 같은 도구 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="12a82-112">그러면 검색 패턴과 일치하는 설치된 앱의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="12a82-113">다른 명령 프롬프트를 찾으려면 `prompt`와 같은 다른 검색어를 입력해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="12a82-114">**Visual Studio용 개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="12a82-115">Windows 8.1에서</span><span class="sxs-lookup"><span data-stu-id="12a82-115">In Windows 8.1</span></span>

1. <span data-ttu-id="12a82-116">Windows 로고 키 ![키보드에서 Windows 로고 키](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="12a82-117">예를 들어 키보드에서</span><span class="sxs-lookup"><span data-stu-id="12a82-117">on your keyboard for example.</span></span>

2. <span data-ttu-id="12a82-118">**시작** 화면에서 **Ctrl**+**Tab**을 눌러 **앱** 목록을 열고 `V`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-118">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="12a82-119">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="12a82-120">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="12a82-121">Windows 8에서</span><span class="sxs-lookup"><span data-stu-id="12a82-121">In Windows 8</span></span>

1. <span data-ttu-id="12a82-122">Windows 로고 키 ![키보드에서 Windows 로고 키](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="12a82-123">예를 들어 키보드에서</span><span class="sxs-lookup"><span data-stu-id="12a82-123">on your keyboard for example.</span></span>

2. <span data-ttu-id="12a82-124">**시작** 화면에서 Windows 로고 키 ![키보드에서 로고 키](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-124">On the **Start** screen, press the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="12a82-125">`+ Z`.</span><span class="sxs-lookup"><span data-stu-id="12a82-125">`+ Z`.</span></span>

3. <span data-ttu-id="12a82-126">화면 아래쪽에서 **앱 보기** 아이콘을 선택하고 `V` 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-126">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="12a82-127">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-127">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="12a82-128">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-128">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="12a82-129">Windows 7에서</span><span class="sxs-lookup"><span data-stu-id="12a82-129">In Windows 7</span></span>

1. <span data-ttu-id="12a82-130">**시작**을 선택하고 **모든 프로그램**, **Microsoft Visual Studio**를 차례로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-130">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="12a82-131">설치한 Visual Studio 버전에 따라 **Visual Studio Tools**, **Visual Studio 명령 프롬프트** 또는 사용할 명령 프롬프트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-131">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="12a82-132">[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 또는 [이전 버전](https://developer.microsoft.com/windows/downloads/sdk-archive)과 같은 다른 SDK를 설치한 경우 ARM, x86 또는 x64 아키텍처에 대한 추가 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-132">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="12a82-133">각 도구의 설명서를 확인하여 사용할 명령 프롬프트 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-133">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="12a82-134">머신에서 수동으로 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="12a82-134">Manually locate the files on your machine</span></span>

<span data-ttu-id="12a82-135">일반적으로 설치한 명령 프롬프트의 바로 가기는 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools와 같이 Visual Studio에 대한 **시작 메뉴** 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-135">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="12a82-136">하지만 어떤 이유로 명령 프롬프트를 검색했는데 예상된 결과가 나타나지 않는 경우, 컴퓨터에서 수동으로 바로 가기를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-136">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="12a82-137">*VsDevCmd.bat*와 같은 명령 프롬프트 파일의 이름 검색을 시도하거나 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools와 같은 도구 폴더로 이동합니다(경로는 Visual Studio 버전, 에디션 및 설치 위치에 따라 바뀜).</span><span class="sxs-lookup"><span data-stu-id="12a82-137">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="12a82-138">Visual Studio 내에서 명령 프롬프트 실행</span><span class="sxs-lookup"><span data-stu-id="12a82-138">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="12a82-139">Visual Studio 개발자 명령 프롬프트 또는 다른 명령 프롬프트를 Visual Studio의 **도구** 메뉴에 추가하면 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-139">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="12a82-140">도구를 사용 가능하도록 하려면 외부 도구 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-140">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="12a82-141">단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-141">Here are the steps:</span></span>

1. <span data-ttu-id="12a82-142">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-142">Open Visual Studio.</span></span>

2. <span data-ttu-id="12a82-143">**도구** 메뉴를 선택한 다음, **외부 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-143">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="12a82-144">**외부 도구** 대화 상자에서 **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-144">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="12a82-145">새 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-145">A new entry appears.</span></span>

4. <span data-ttu-id="12a82-146">`Command Prompt`와 같은 새 메뉴 항목에 대해 **제목**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-146">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="12a82-147">**명령** 필드에서 `%comspec%` 또는 `C:\Windows\System32\cmd.exe` 등의 시작하려는 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-147">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="12a82-148">**인수** 필드에서 `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"`과 같이 사용할 특정 명령 프롬프트가 있는 위치를 지정합니다(이 명령은 Visual Studio 2017 Enterprise와 함께 설치된 개발자 명령 프롬프트를 시작함).</span><span class="sxs-lookup"><span data-stu-id="12a82-148">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="12a82-149">Visual Studio 버전, 에디션 및 설치 위치에 따라 이 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-149">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="12a82-150">**프로젝트 디렉터리**와 같은 **초기 디렉터리** 필드에 대한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-150">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="12a82-151">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-151">Choose the **OK** button.</span></span>

   <span data-ttu-id="12a82-152">새 메뉴 항목이 추가되고 **도구** 메뉴에서 명령 프롬프트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12a82-152">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Visual Studio의 명령 프롬프트 메뉴 항목](./media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="12a82-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12a82-154">See also</span></span>

- [<span data-ttu-id="12a82-155">도구</span><span class="sxs-lookup"><span data-stu-id="12a82-155">Tools</span></span>](index.md)
- [<span data-ttu-id="12a82-156">외부 도구 관리</span><span class="sxs-lookup"><span data-stu-id="12a82-156">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
