---
title: 지역화된 IntelliSense 파일 설치
description: Visual Studio에서 .NET 5 이상 프로젝트(.NET Core 포함)에 대해 지역화된 IntelliSense 파일을 사용하도록 개발 머신을 설정하는 방법을 알아봅니다.
ms.date: 11/06/2020
ms.openlocfilehash: 45eeae12ca79179cacb3d48fca28118de70e0a4f
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506768"
---
# <a name="how-to-install-localized-intellisense-files-for-net"></a><span data-ttu-id="0717f-103">.NET에 대해 지역화된 IntelliSense 파일을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="0717f-103">How to install localized IntelliSense files for .NET</span></span>

<span data-ttu-id="0717f-104">[IntelliSense](/visualstudio/ide/using-intellisense)는 Visual Studio 등 여러 IDE(통합 개발 환경)에서 사용할 수 있는 코드 완성 지원 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that's available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="0717f-105">기본적으로 .NET 프로젝트를 개발할 때 SDK에는 영어 버전의 IntelliSense 파일만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-105">By default, when you're developing .NET projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="0717f-106">이 문서는 다음 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-106">This article explains:</span></span>

- <span data-ttu-id="0717f-107">이러한 파일의 지역화된 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="0717f-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="0717f-108">다른 언어를 사용하도록 Visual Studio 설치를 수정하는 방법</span><span class="sxs-lookup"><span data-stu-id="0717f-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0717f-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0717f-109">Prerequisites</span></span>

- <span data-ttu-id="0717f-110">[.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)와 같은 [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version, such as [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0).</span></span>
- <span data-ttu-id="0717f-111">[Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0717f-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="0717f-112">지역화된 IntelliSense 파일 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="0717f-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0717f-113">IntelliSense 파일을 .NET 설치 폴더로 복사하려면 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET installation folder.</span></span>

1. <span data-ttu-id="0717f-114">[IntelliSense 파일 다운로드](https://dotnet.microsoft.com/download/intellisense) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/intellisense) page.</span></span>

1. <span data-ttu-id="0717f-115">사용할 언어 및 버전에 대한 IntelliSense 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="0717f-116">Zip 파일의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="0717f-117">.NET Intellisense 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-117">Navigate to the .NET Intellisense folder.</span></span>

   1. <span data-ttu-id="0717f-118">.NET 설치 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-118">Navigate to the .NET installation folder.</span></span> <span data-ttu-id="0717f-119">기본적으로 *%ProgramFiles%\dotnet\packs* 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="0717f-120">IntelliSense를 설치할 SDK를 선택하고 연결 경로로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="0717f-121">다음과 같은 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-121">You have the following options:</span></span>

      | <span data-ttu-id="0717f-122">SDK 형식</span><span class="sxs-lookup"><span data-stu-id="0717f-122">SDK type</span></span>              | <span data-ttu-id="0717f-123">경로</span><span class="sxs-lookup"><span data-stu-id="0717f-123">Path</span></span>                               |
      |-----------------------|------------------------------------|
      | <span data-ttu-id="0717f-124">.NET 5 이상 및 .NET Core</span><span class="sxs-lookup"><span data-stu-id="0717f-124">.NET 5+ and .NET Core</span></span> | <span data-ttu-id="0717f-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="0717f-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="0717f-126">Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="0717f-126">Windows Desktop</span></span>       | <span data-ttu-id="0717f-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="0717f-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="0717f-128">.NET 표준</span><span class="sxs-lookup"><span data-stu-id="0717f-128">.NET Standard</span></span>         | <span data-ttu-id="0717f-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="0717f-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="0717f-130">지역화된 IntelliSense를 설치하려는 버전으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="0717f-131">예: *5.0.0*</span><span class="sxs-lookup"><span data-stu-id="0717f-131">For example, *5.0.0*.</span></span>
   1. <span data-ttu-id="0717f-132">*ref* 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="0717f-133">모니커 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-133">Open the moniker folder.</span></span> <span data-ttu-id="0717f-134">예를 들어 *NET 5.0* 이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-134">For example, *net5.0*.</span></span>

   <span data-ttu-id="0717f-135">이동하는 전체 경로는 *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0* 과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.</span></span>

1. <span data-ttu-id="0717f-136">방금 연 모니커 폴더 안에 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="0717f-137">폴더 이름은 사용하려는 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="0717f-138">다음 표에서는 다양한 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="0717f-139">언어</span><span class="sxs-lookup"><span data-stu-id="0717f-139">Language</span></span>              | <span data-ttu-id="0717f-140">폴더 이름</span><span class="sxs-lookup"><span data-stu-id="0717f-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="0717f-141">포르투갈어(브라질)</span><span class="sxs-lookup"><span data-stu-id="0717f-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="0717f-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="0717f-142">*pt-br*</span></span>     |
   | <span data-ttu-id="0717f-143">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="0717f-143">Chinese (simplified)</span></span>  | <span data-ttu-id="0717f-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="0717f-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="0717f-145">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="0717f-145">Chinese (traditional)</span></span> | <span data-ttu-id="0717f-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="0717f-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="0717f-147">프랑스어</span><span class="sxs-lookup"><span data-stu-id="0717f-147">French</span></span>                | <span data-ttu-id="0717f-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="0717f-148">*fr*</span></span>        |
   | <span data-ttu-id="0717f-149">독일어</span><span class="sxs-lookup"><span data-stu-id="0717f-149">German</span></span>                | <span data-ttu-id="0717f-150">*de*</span><span class="sxs-lookup"><span data-stu-id="0717f-150">*de*</span></span>        |
   | <span data-ttu-id="0717f-151">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="0717f-151">Italian</span></span>               | <span data-ttu-id="0717f-152">*it*</span><span class="sxs-lookup"><span data-stu-id="0717f-152">*it*</span></span>        |
   | <span data-ttu-id="0717f-153">일본어</span><span class="sxs-lookup"><span data-stu-id="0717f-153">Japanese</span></span>              | <span data-ttu-id="0717f-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="0717f-154">*ja*</span></span>        |
   | <span data-ttu-id="0717f-155">한국어</span><span class="sxs-lookup"><span data-stu-id="0717f-155">Korean</span></span>                | <span data-ttu-id="0717f-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="0717f-156">*ko*</span></span>        |
   | <span data-ttu-id="0717f-157">러시아어</span><span class="sxs-lookup"><span data-stu-id="0717f-157">Russian</span></span>               | <span data-ttu-id="0717f-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="0717f-158">*ru*</span></span>        |
   | <span data-ttu-id="0717f-159">스페인어</span><span class="sxs-lookup"><span data-stu-id="0717f-159">Spanish</span></span>               | <span data-ttu-id="0717f-160">*es*</span><span class="sxs-lookup"><span data-stu-id="0717f-160">*es*</span></span>        |

1. <span data-ttu-id="0717f-161">3단계에서 추출한 *.xml* 파일을 이 새 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-161">Copy the *.xml* files you extracted in step 3 to this new folder.</span></span> <span data-ttu-id="0717f-162">*.xml* 파일이 SDK 폴더별로 분할되므로 4단계에서 선택한 일치하는 SDK로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose in step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="0717f-163">Visual Studio 언어 수정</span><span class="sxs-lookup"><span data-stu-id="0717f-163">Modify Visual Studio language</span></span>

<span data-ttu-id="0717f-164">Visual Studio에서 IntelliSense에 다른 언어를 사용하도록 하려면 적절한 언어 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="0717f-165">이 작업은 [설치 중](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional)에 수행하거나 Visual Studio 설치를 수정하여 나중에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="0717f-166">선택한 언어로 Visual Studio를 이미 구성한 경우 IntelliSense 설치가 준비됩니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="0717f-167">언어 팩 설치</span><span class="sxs-lookup"><span data-stu-id="0717f-167">Install the language pack</span></span>

<span data-ttu-id="0717f-168">설치하는 동안 원하는 언어 팩을 설치하지 않은 경우 다음과 같이 Visual Studio를 업데이트하여 언어 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0717f-169">Visual Studio를 설치, 업데이트 또는 수정하려면 관리자 권한이 있는 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="0717f-170">자세한 내용은 [사용자 권한 및 Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0717f-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="0717f-171">컴퓨터에서 Visual Studio 설치 관리자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="0717f-172">예를 들어 Windows 10을 실행하는 컴퓨터에서 **시작** 을 선택한 다음, **Visual Studio 설치 관리자** 로 나열되는 **V** 문자로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-172">For example, on a computer running Windows 10, select **Start** , and then scroll to the letter **V** , where it's listed as **Visual Studio Installer**.</span></span>

   ![Windows에서 Visual Studio 설치 관리자 열기](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="0717f-174">다음 위치에서 Visual Studio 설치 관리자를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="0717f-175">계속하기 전에 설치 관리자를 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="0717f-176">그렇다면 지시를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0717f-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="0717f-177">설치 관리자에서 언어 팩을 추가하려는 Visual Studio의 버전을 찾은 다음, **수정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Visual Studio 업데이트 또는 수정](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="0717f-179">**수정** 단추가 표시되지 않고 **업데이트** 단추가 대신 표시되는 경우, Visual Studio를 업데이트해야만 설치를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="0717f-180">업데이트가 완료되면 **수정** 단추가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="0717f-181">**언어 팩** 탭에서 설치하거나 제거하려는 언어를 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Visual Studio 언어 팩 탭](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="0717f-183">**수정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-183">Choose **Modify**.</span></span> <span data-ttu-id="0717f-184">업데이트가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="0717f-185">Visual Studio에서 언어 설정 수정</span><span class="sxs-lookup"><span data-stu-id="0717f-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="0717f-186">원하는 언어 팩을 설치했으면 다른 언어를 사용하도록 Visual Studio 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="0717f-187">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="0717f-188">시작 창에서 **코드를 사용하지 않고 계속** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="0717f-189">메뉴 모음에서 **도구** > **옵션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="0717f-190">[옵션] 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="0717f-191">**환경** 노드 아래에서 **국가별 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="0717f-192">**언어** 드롭다운에서 원하는 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="0717f-193">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-193">Choose **OK**.</span></span>

1. <span data-ttu-id="0717f-194">변경 내용을 적용하려면 Visual Studio를 다시 시작해야 함을 알리는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="0717f-195">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-195">Choose **OK**.</span></span>

1. <span data-ttu-id="0717f-196">Visual Studio를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-196">Restart Visual Studio.</span></span>

<span data-ttu-id="0717f-197">그러면 방금 설치한 IntelliSense 파일의 버전을 대상으로 하는 .NET 프로젝트를 열 때 IntelliSense가 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0717f-197">After this, your IntelliSense should work as expected when you open a .NET project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0717f-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0717f-198">See also</span></span>

- [<span data-ttu-id="0717f-199">Visual Studio의 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="0717f-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
