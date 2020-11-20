---
title: '자습서: .NET 로컬 도구 설치 및 사용'
description: .NET 도구를 로컬 도구로 설치하고 사용하는 방법을 알아봅니다.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 2cb25443706293b66325d43136afcd3fd886294d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633883"
---
# <a name="tutorial-install-and-use-a-net-local-tool-using-the-net-cli"></a><span data-ttu-id="f7a09-103">자습서: .NET CLI를 사용하여 .NET 로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="f7a09-103">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>

<span data-ttu-id="f7a09-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f7a09-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="f7a09-105">이 자습서에서는 로컬 도구를 설치하고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="f7a09-106">[이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)에서 만든 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7a09-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7a09-107">Prerequisites</span></span>

* <span data-ttu-id="f7a09-108">[이 시리즈의 첫 번째 자습서](global-tools-how-to-create.md)를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="f7a09-109">.NET Core 2.1 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="f7a09-110">이 자습서에서는 .NET Core 2.1을 대상으로 하는 도구를 설치하고 사용하므로 해당 런타임이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="f7a09-111">2\.1 런타임을 설치하려면 [.NET Core 2.1 다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core/2.1)로 이동하여 **앱 실행 - 런타임** 열에서 런타임 설치 링크를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="f7a09-112">매니페스트 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7a09-112">Create a manifest file</span></span>

<span data-ttu-id="f7a09-113">로컬 액세스 전용(현재 디렉터리 및 하위 디렉터리용) 도구를 설치하려면 매니페스트 파일에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span>

<span data-ttu-id="f7a09-114">*microsoft.botsay* 폴더에서 한 수준 위인 *repository* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-114">From the *microsoft.botsay* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="f7a09-115">[dotnet new](dotnet-new.md) 명령을 실행하여 매니페스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="f7a09-116">출력은 파일을 성공적으로 생성했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="f7a09-117">*.config/dotnet-tools.json* 파일에 아직 도구가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="f7a09-118">매니페스트 파일에 나열된 도구는 현재 디렉터리와 하위 디렉터리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="f7a09-119">현재 디렉터리는 매니페스트 파일이 있는 *.config* 디렉터리를 포함하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="f7a09-120">로컬 도구를 참조하는 CLI 명령을 사용하는 경우 SDK는 현재 디렉터리와 부모 디렉터리에서 매니페스트 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="f7a09-121">매니페스트 파일을 찾았지만 파일이 참조된 도구를 포함하지 않는 경우 부모 디렉터리까지 검색을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="f7a09-122">참조된 도구를 찾거나 `isRoot`가 `true`로 설정된 매니페스트 파일을 찾으면 검색이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="f7a09-123">로컬 도구로 botsay 설치</span><span class="sxs-lookup"><span data-stu-id="f7a09-123">Install botsay as a local tool</span></span>

<span data-ttu-id="f7a09-124">첫 번째 자습서에서 만든 패키지에서 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

<span data-ttu-id="f7a09-125">이 명령은 이전 단계에서 만든 매니페스트 파일에 도구를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="f7a09-126">명령 출력에는 새로 설치된 도구가 있는 매니페스트 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="f7a09-127">이제 *.config/dotnet-tools.json* 파일에 도구가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="f7a09-128">도구 사용</span><span class="sxs-lookup"><span data-stu-id="f7a09-128">Use the tool</span></span>

<span data-ttu-id="f7a09-129">*repository* 폴더에서 `dotnet tool run` 명령을 실행하여 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="f7a09-130">다른 사용자가 설치한 로컬 도구 복원</span><span class="sxs-lookup"><span data-stu-id="f7a09-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="f7a09-131">일반적으로 로컬 도구는 리포지토리의 루트 디렉터리에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="f7a09-132">매니페스트 파일을 리포지토리에 체크 인하면 다른 개발자가 최신 매니페스트 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="f7a09-133">매니페스트 파일에 나열된 모든 도구를 설치하기 위해 단일 `dotnet tool restore` 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="f7a09-134">*.config/dotnet-tools.json* 파일을 열고 내용을 다음 JSON으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="f7a09-135">`<name>`을 프로젝트를 만드는 데 사용한 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="f7a09-136">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-136">Save your changes.</span></span>

   <span data-ttu-id="f7a09-137">이러한 변경을 수행하는 것은 다른 사용자가 프로젝트 디렉터리에 대한 패키지 `dotnetsay`를 설치한 후 리포지토리의 최신 버전을 가져오는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span>

1. <span data-ttu-id="f7a09-138">`dotnet tool restore` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="f7a09-139">이 명령은 다음 예제와 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="f7a09-140">도구를 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="f7a09-141">출력은 다음 예제와 같은 패키지 및 명령 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="f7a09-142">도구를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="f7a09-143">로컬 도구 업데이트</span><span class="sxs-lookup"><span data-stu-id="f7a09-143">Update a local tool</span></span>

<span data-ttu-id="f7a09-144">로컬 도구 `dotnetsay`의 설치된 버전은 2.1.3입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="f7a09-145">최신 버전은 2.1.4입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="f7a09-146">[dotnet tool update](dotnet-tool-update.md) 명령을 사용하여 도구를 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="f7a09-147">출력은 새 버전 번호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="f7a09-148">이 업데이트 명령은 패키지 ID를 포함하는 첫 번째 매니페스트 파일을 찾아 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="f7a09-149">검색 범위에 있는 매니페스트 파일에 이러한 패키지 ID가 없는 경우 SDK는 가장 가까운 매니페스트 파일에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="f7a09-150">`isRoot = true`로 설정된 매니페스트 파일을 찾을 때까지 검색 범위는 부모 디렉터리까지 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="f7a09-151">로컬 도구 제거</span><span class="sxs-lookup"><span data-stu-id="f7a09-151">Remove local tools</span></span>

<span data-ttu-id="f7a09-152">[dotnet tool uninstall](dotnet-tool-uninstall.md) 명령을 실행하여 설치된 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a09-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="f7a09-153">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f7a09-153">Troubleshoot</span></span>

<span data-ttu-id="f7a09-154">자습서를 수행하는 동안 오류 메시지가 표시되는 경우 [.NET 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7a09-154">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7a09-155">참조</span><span class="sxs-lookup"><span data-stu-id="f7a09-155">See also</span></span>

<span data-ttu-id="f7a09-156">자세한 내용은 [.NET Core 도구](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7a09-156">For more information, see [.NET Core tools](global-tools.md)</span></span>
