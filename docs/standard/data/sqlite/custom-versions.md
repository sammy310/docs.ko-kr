---
title: 사용자 지정 SQLite 버전
ms.date: 05/14/2020
description: 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 15db10db26bc7c5017313ca020a0e1e528ba207a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440839"
---
# <a name="custom-sqlite-versions"></a><span data-ttu-id="0236c-103">사용자 지정 SQLite 버전</span><span class="sxs-lookup"><span data-stu-id="0236c-103">Custom SQLite versions</span></span>

<span data-ttu-id="0236c-104">`Microsoft.Data.Sqlite`는 `SQLitePCLRaw`를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-104">`Microsoft.Data.Sqlite` is built on top of `SQLitePCLRaw`.</span></span> <span data-ttu-id="0236c-105">번들을 사용하거나 `SQLitePCLRaw` 공급자를 구성하여 네이티브 SQLite 라이브러리의 사용자 지정 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-105">You can use custom versions of the native SQLite library by using a bundle or by configuring a `SQLitePCLRaw` provider.</span></span>

## <a name="bundles"></a><span data-ttu-id="0236c-106">번들</span><span class="sxs-lookup"><span data-stu-id="0236c-106">Bundles</span></span>

<span data-ttu-id="0236c-107">`SQLitePCLRaw`는 다양한 플랫폼에서 적절한 종속성을 쉽게 가져올 수 있도록 편의 기반 번들 패키지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-107">`SQLitePCLRaw` provides convenience-based bundle packages, that make it easy to bring in the right dependencies across different platforms.</span></span> <span data-ttu-id="0236c-108">주 `Microsoft.Data.Sqlite` 패키지는 기본적으로 `SQLitePCLRaw.bundle_e_sqlite3`을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-108">The main `Microsoft.Data.Sqlite` package brings in `SQLitePCLRaw.bundle_e_sqlite3` by default.</span></span> <span data-ttu-id="0236c-109">다른 번들을 사용하려면 사용하려는 번들 패키지와 함께 `Microsoft.Data.Sqlite.Core` 패키지를 대신 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-109">To use a different bundle, install the `Microsoft.Data.Sqlite.Core` package instead along with the bundle package you want to use.</span></span> <span data-ttu-id="0236c-110">번들은 `Microsoft.Data.Sqlite`에 의해 자동으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-110">Bundles are automatically initialized by `Microsoft.Data.Sqlite`.</span></span>

| <span data-ttu-id="0236c-111">번들</span><span class="sxs-lookup"><span data-stu-id="0236c-111">Bundle</span></span> | <span data-ttu-id="0236c-112">설명</span><span class="sxs-lookup"><span data-stu-id="0236c-112">Description</span></span> |
|--|--|
| [<span data-ttu-id="0236c-113">SQLitePCLRaw.bundle_e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="0236c-113">SQLitePCLRaw.bundle_e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | <span data-ttu-id="0236c-114">모든 플랫폼에서 SQLite의 일관된 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-114">Provides a consistent version of SQLite on all platforms.</span></span> <span data-ttu-id="0236c-115">FTS4, FTS5, JSON1 및 R\*Tree 확장을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-115">Includes the FTS4, FTS5, JSON1, and R\*Tree extensions.</span></span> <span data-ttu-id="0236c-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-116">This is the default.</span></span> |
| [<span data-ttu-id="0236c-117">SQLitePCLRaw.bundle_e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="0236c-117">SQLitePCLRaw.bundle_e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | <span data-ttu-id="0236c-118">`SQLCipher`의 비공식 오픈 소스 빌드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-118">Provides an unofficial, open-source build of `SQLCipher`.</span></span> |
| [<span data-ttu-id="0236c-119">SQLitePCLRaw.bundle_green</span><span class="sxs-lookup"><span data-stu-id="0236c-119">SQLitePCLRaw.bundle_green</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | <span data-ttu-id="0236c-120">iOS에서 시스템 SQLite 라이브러리를 사용하는 것을 제외하고 `bundle_e_sqlite3`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-120">Same as `bundle_e_sqlite3`, except on iOS where it uses the system SQLite library.</span></span> |
| [<span data-ttu-id="0236c-121">SQLitePCLRaw.bundle_winsqlite3</span><span class="sxs-lookup"><span data-stu-id="0236c-121">SQLitePCLRaw.bundle_winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | <span data-ttu-id="0236c-122">Windows 10의 시스템 SQLite 라이브러리인 `winsqlite3.dll`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-122">Uses `winsqlite3.dll`, the system SQLite library on Windows 10.</span></span> |
| [<span data-ttu-id="0236c-123">SQLitePCLRaw.bundle_zetetic</span><span class="sxs-lookup"><span data-stu-id="0236c-123">SQLitePCLRaw.bundle_zetetic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | <span data-ttu-id="0236c-124">Zetetic의 공식 `SQLCipher` 빌드를 사용합니다(포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0236c-124">Uses the official `SQLCipher` builds from Zetetic (not included).</span></span> |

<span data-ttu-id="0236c-125">예를 들어 비공식 오픈 소스 `SQLCipher` 빌드를 사용하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-125">For example, to use the unofficial, open-source build of `SQLCipher` use the following commands.</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="0236c-126">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0236c-126">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="0236c-127">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0236c-127">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-available-providers"></a><span data-ttu-id="0236c-128">사용 가능한 SQLitePCLRaw 공급자</span><span class="sxs-lookup"><span data-stu-id="0236c-128">SQLitePCLRaw available providers</span></span>

<span data-ttu-id="0236c-129">번들을 사용하지 않는 경우 핵심 어셈블리에서 SQLite의 사용 가능한 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-129">When not relying on a bundle, you can use the available providers of SQLite with the core assembly.</span></span>

| <span data-ttu-id="0236c-130">공급자</span><span class="sxs-lookup"><span data-stu-id="0236c-130">Provider</span></span> | <span data-ttu-id="0236c-131">설명</span><span class="sxs-lookup"><span data-stu-id="0236c-131">Description</span></span> |
|--|--|
| [<span data-ttu-id="0236c-132">SQLitePCLRaw.provider.dynamic</span><span class="sxs-lookup"><span data-stu-id="0236c-132">SQLitePCLRaw.provider.dynamic</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | <span data-ttu-id="0236c-133">`dynamic` 공급자는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> 특성을 사용하는 대신 네이티브 라이브러리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-133">The `dynamic` provider loads the native library instead of using <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType> attributes.</span></span> <span data-ttu-id="0236c-134">이 공급자를 사용하는 방법에 대한 자세한 내용은 [동적 공급자 사용](#use-the-dynamic-provider)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0236c-134">For more information on using this provider, see [use the dynamic provider](#use-the-dynamic-provider).</span></span> |
| [<span data-ttu-id="0236c-135">SQLitePCLRaw.provider.e_sqlite3</span><span class="sxs-lookup"><span data-stu-id="0236c-135">SQLitePCLRaw.provider.e_sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | <span data-ttu-id="0236c-136">기본 공급자는 `e_sqlite3`입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-136">The `e_sqlite3` is the default provider.</span></span> |
| [<span data-ttu-id="0236c-137">SQLitePCLRaw.provider.e_sqlcipher</span><span class="sxs-lookup"><span data-stu-id="0236c-137">SQLitePCLRaw.provider.e_sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | <span data-ttu-id="0236c-138">`e_sqlcipher` 공급자는 비공식적이고 지원되지 않는 `SQLCipher`입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-138">The `e_sqlcipher` provider is the unofficial and unsupported `SQLCipher`.</span></span> |
| [<span data-ttu-id="0236c-139">SQLitePCLRaw.provider.sqlite3</span><span class="sxs-lookup"><span data-stu-id="0236c-139">SQLitePCLRaw.provider.sqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | <span data-ttu-id="0236c-140">`sqlite3` 공급자는 iOS, macOS 및 Linux용 시스템 제공 `SQLite`입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-140">The `sqlite3` provider is a system-provided `SQLite` for iOS, macOS, and Linux.</span></span> |
| [<span data-ttu-id="0236c-141">SQLitePCLRaw.provider.sqlcipher</span><span class="sxs-lookup"><span data-stu-id="0236c-141">SQLitePCLRaw.provider.sqlcipher</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | <span data-ttu-id="0236c-142">`sqlcipher` 공급자는 `Zetetic`의 공식 `SQLCipher` 빌드를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-142">The `sqlcipher` provider is for official `SQLCipher` builds from `Zetetic`.</span></span> |
| [<span data-ttu-id="0236c-143">SQLitePCLRaw.provider.winsqlite3</span><span class="sxs-lookup"><span data-stu-id="0236c-143">SQLitePCLRaw.provider.winsqlite3</span></span>](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | <span data-ttu-id="0236c-144">`winsqlite3` 공급자는 Windows 10 환경을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-144">The `winsqlite3` provider is for Windows 10 environments.</span></span> |

<span data-ttu-id="0236c-145">`sqlite3` 공급자를 사용하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-145">To use the `sqlite3` provider use the following commands:</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="0236c-146">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0236c-146">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[<span data-ttu-id="0236c-147">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0236c-147">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

<span data-ttu-id="0236c-148">패키지가 설치되면 공급자를 `sqlite3` 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-148">With the packages installed, you then set the provider to the `sqlite3` instance.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a><span data-ttu-id="0236c-149">동적 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="0236c-149">Use the dynamic provider</span></span>

<span data-ttu-id="0236c-150">`SQLitePCLRaw.provider.dynamic_cdecl` 패키지를 활용하여 자체 SQLite 빌드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-150">You can use your own build of SQLite by leveraging the `SQLitePCLRaw.provider.dynamic_cdecl` package.</span></span> <span data-ttu-id="0236c-151">이 경우 네이티브 라이브러리를 앱과 함께 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-151">In this case, you're responsible for deploying the native library with your app.</span></span> <span data-ttu-id="0236c-152">단, 앱과 함께 네이티브 라이브러리를 배포하는 세부 방법은 사용 중인 .NET 플랫폼 및 런타임에 따라 크게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-152">Note, the details of deploying native libraries with your app vary considerably depending on which .NET platform and runtime you're using.</span></span>

<span data-ttu-id="0236c-153">먼저 `IGetFunctionPointer`를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-153">First, you'll need to implement `IGetFunctionPointer`.</span></span> <span data-ttu-id="0236c-154">.NET Core에서의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-154">The implementation on .NET Core is as follows:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

<span data-ttu-id="0236c-155">그런 다음 `SQLitePCLRaw` 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-155">Next, configure the `SQLitePCLRaw` provider.</span></span> <span data-ttu-id="0236c-156">앱에서 `Microsoft.Data.Sqlite`를 사용하기 전에 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-156">Ensure this is done before `Microsoft.Data.Sqlite` is used in your app.</span></span> <span data-ttu-id="0236c-157">또한 공급자를 재정의할 수 있는 `SQLitePCLRaw` 번들 패키지를 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0236c-157">Also, avoid using a `SQLitePCLRaw` bundle package which might override your provider.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
