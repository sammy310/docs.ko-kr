---
title: Windows 시스템의 파일 경로 형식
description: 이 문서에서는 기존 DOS 경로, DOS 디바이스 경로 및 UNC(범용 명명 규칙) 경로와 같은 Windows 시스템의 파일 경로 서식에 대해 알아봅니다.
ms.date: 06/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, long paths
- long paths
- path formats, Windows
ms.openlocfilehash: e24772ee9c9d22786c9cfece43017f8526434601
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188057"
---
# <a name="file-path-formats-on-windows-systems"></a><span data-ttu-id="2635e-103">Windows 시스템의 파일 경로 형식</span><span class="sxs-lookup"><span data-stu-id="2635e-103">File path formats on Windows systems</span></span>

<span data-ttu-id="2635e-104"><xref:System.IO> 네임스페이스에 있는 많은 유형의 멤버는 파일 시스템 리소스에 대한 절대 또는 상대 경로를 지정할 수 있는 `path` 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-104">Members of many of the types in the <xref:System.IO> namespace include a `path` parameter that lets you specify an absolute or relative path to a file system resource.</span></span> <span data-ttu-id="2635e-105">이 경로는 [Windows 파일 시스템 API](/windows/desktop/fileio/file-systems)에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-105">This path is then passed to [Windows file system APIs](/windows/desktop/fileio/file-systems).</span></span> <span data-ttu-id="2635e-106">이 토픽에서는 Windows 시스템에 사용할 수 있는 파일 경로의 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-106">This topic discusses the formats for file paths that you can use on Windows systems.</span></span>

## <a name="traditional-dos-paths"></a><span data-ttu-id="2635e-107">기존 DOS 경로</span><span class="sxs-lookup"><span data-stu-id="2635e-107">Traditional DOS paths</span></span>

<span data-ttu-id="2635e-108">표준 DOS 경로는 다음 세 구성 요소로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-108">A standard DOS path can consist of three components:</span></span>

- <span data-ttu-id="2635e-109">볼륨 또는 드라이브 문자 다음에 볼륨 구분 기호(`:`).</span><span class="sxs-lookup"><span data-stu-id="2635e-109">A volume or drive letter followed by the volume separator (`:`).</span></span>
- <span data-ttu-id="2635e-110">디렉터리 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-110">A directory name.</span></span> <span data-ttu-id="2635e-111">[디렉터리 구분 문자](<xref:System.IO.Path.DirectorySeparatorChar>)는 중첩된 디렉터리 계층 내에서 하위 디렉터리를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-111">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates subdirectories within the nested directory hierarchy.</span></span>
- <span data-ttu-id="2635e-112">선택적 파일 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-112">An optional filename.</span></span> <span data-ttu-id="2635e-113">[디렉터리 구분 문자](<xref:System.IO.Path.DirectorySeparatorChar>)는 파일 경로 및 파일 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-113">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates the file path and the filename.</span></span>

<span data-ttu-id="2635e-114">세 구성 요소가 모두 존재하면 절대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-114">If all three components are present, the path is absolute.</span></span> <span data-ttu-id="2635e-115">볼륨 또는 드라이브 문자가 지정되지 않았으며 디렉터리 이름이 [디렉터리 구분 문자](<xref:System.IO.Path.DirectorySeparatorChar>)로 시작하는 경우 현재 드라이브의 루트에 대한 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-115">If no volume or drive letter is specified and the directory name begins with the [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>), the path is relative from the root of the current drive.</span></span> <span data-ttu-id="2635e-116">그렇지 않으면 현재 디렉터리를 기준으로 하는 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-116">Otherwise, the path is relative to the current directory.</span></span> <span data-ttu-id="2635e-117">다음 표는 몇몇 가능한 디렉터리 및 파일 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-117">The following table shows some possible directory and file paths.</span></span>

|<span data-ttu-id="2635e-118">Path</span><span class="sxs-lookup"><span data-stu-id="2635e-118">Path</span></span>  |<span data-ttu-id="2635e-119">설명</span><span class="sxs-lookup"><span data-stu-id="2635e-119">Description</span></span>  |
| -- | -- |
| `C:\Documents\Newsletters\Summer2018.pdf` | <span data-ttu-id="2635e-120">`C:` 드라이브의 루트에서 시작하는 절대 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-120">An absolute file path from the root of drive `C:`.</span></span> |
| `\Program Files\Custom Utilities\StringFinder.exe` | <span data-ttu-id="2635e-121">현재 드라이브의 루트에서 시작하는 절대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-121">An absolute path from the root of the current drive.</span></span> |
| `2018\January.xlsx` | <span data-ttu-id="2635e-122">현재 디렉터리의 하위 디렉터리에 있는 파일에 대한 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-122">A relative path to a file in a subdirectory of the current directory.</span></span> |
| `..\Publications\TravelBrochure.pdf` | <span data-ttu-id="2635e-123">현재 디렉터리의 피어인 디렉터리에 있는 파일에 대한 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-123">A relative path to file in a directory that is a peer of the current directory.</span></span> |
| `C:\Projects\apilibrary\apilibrary.sln` | <span data-ttu-id="2635e-124">`C:` 드라이브의 루트에서 시작하는 파일의 절대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-124">An absolute path to a file from the root of drive `C:`.</span></span> |
| `C:Projects\apilibrary\apilibrary.sln` | <span data-ttu-id="2635e-125">`C:` 드라이브의 현재 디렉터리에서 시작하는 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-125">A relative path from the current directory of the `C:` drive.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="2635e-126">마지막 두 경로 간의 차이점에 주목하십시오.</span><span class="sxs-lookup"><span data-stu-id="2635e-126">Note the difference between the last two paths.</span></span> <span data-ttu-id="2635e-127">둘 다 선택적 볼륨 지정자(두 경우 모두 `C:`)를 지정하지만 첫 번째 경로는 지정한 볼륨의 루트에서 시작하는 반면, 두 번째 경로는 그러지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-127">Both specify the optional volume specifier (`C:` in both cases), but the first begins with the root of the specified volume, whereas the second does not.</span></span> <span data-ttu-id="2635e-128">따라서 첫 번째 경로는 `C:` 드라이브의 루트 디렉터리에서 시작하는 절대 경로인 반면, 두 번째 경로는 `C:` 드라이브의 현재 디렉터리에서 시작하는 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-128">As result, the first is an absolute path from the root directory of drive `C:`, whereas the second is a relative path from the current directory of drive `C:`.</span></span> <span data-ttu-id="2635e-129">첫 번째 경로가 의도한 두 번째 양식을 사용하는 것은 Windows 파일 경로를 수반하는 버그의 일반적인 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-129">Use of the second form when the first is intended is a common source of bugs that involve Windows file paths.</span></span>

<span data-ttu-id="2635e-130"><xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWithType> 메서드를 호출하여 파일 경로가 정규화되는지(즉, 경로가 현재 디렉터리와 독립적이며 현재 디렉터리가 변경되어도 변경되지 않음) 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-130">You can determine whether a file path is fully qualified (that is, it the path is independent of the current directory and does not change when the current directory changes) by calling the <xref:System.IO.Path.IsPathFullyQualified%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2635e-131">참고로 그러한 경로는 상대 디렉터리 세그먼트(`.` 및 `..`)를 포함할 수 있으며 확인된 경로가 언제나 같은 위치를 가리키는 경우 여전히 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-131">Note that such a path can include relative directory segments (`.` and `..`) and still be fully qualified if the resolved path always points to the same location.</span></span>

<span data-ttu-id="2635e-132">다음 예제에서는 절대 경로와 상대 경로 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-132">The following example illustrates the difference between absolute and relative paths.</span></span> <span data-ttu-id="2635e-133">`D:\FY2018\` 디렉터리가 있고, 예제를 실행하기 전에 명령 프롬프트에서 `D:\`의 현재 디렉터리를 설정하지 않았다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-133">It assumes that the directory `D:\FY2018\` exists, and that you haven't set any current directory for `D:\` from the command prompt before running the example.</span></span>

[!code-csharp[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/cs/paths.cs)]
[!code-vb[absolute-and-relative-paths](~/samples/snippets/standard/io/file-names/vb/paths.vb)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="unc-paths"></a><span data-ttu-id="2635e-134">UNC 경로</span><span class="sxs-lookup"><span data-stu-id="2635e-134">UNC paths</span></span>

<span data-ttu-id="2635e-135">네트워크 리소스에 액세스하기 위해 사용하는 UNC(범용 명명 규칙) 경로는 다음과 같은 형식을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-135">Universal naming convention (UNC) paths, which are used to access network resources, have the following format:</span></span>

- <span data-ttu-id="2635e-136">`\\`로 시작하는 서버 또는 호스트 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-136">A server or host name, which is prefaced by `\\`.</span></span> <span data-ttu-id="2635e-137">서버 이름에 NetBIOS 컴퓨터 이름 또는 IP/FQDN 주소(IPv4 및 v6을 지원함)가 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-137">The server name can be a NetBIOS machine name or an IP/FQDN address (IPv4 as well as v6 are supported).</span></span>
- <span data-ttu-id="2635e-138">`\`에 의해 호스트 이름과 구분되는 공유 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-138">A share name, which is separated from the host name by `\`.</span></span> <span data-ttu-id="2635e-139">서버 이름과 공유 이름이 함께 볼륨을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-139">Together, the server and share name make up the volume.</span></span>
- <span data-ttu-id="2635e-140">디렉터리 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-140">A directory name.</span></span> <span data-ttu-id="2635e-141">[디렉터리 구분 문자](<xref:System.IO.Path.DirectorySeparatorChar>)는 중첩된 디렉터리 계층 내에서 하위 디렉터리를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-141">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates subdirectories within the nested directory hierarchy.</span></span>
- <span data-ttu-id="2635e-142">선택적 파일 이름.</span><span class="sxs-lookup"><span data-stu-id="2635e-142">An optional filename.</span></span> <span data-ttu-id="2635e-143">[디렉터리 구분 문자](<xref:System.IO.Path.DirectorySeparatorChar>)는 파일 경로 및 파일 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-143">The [directory separator character](<xref:System.IO.Path.DirectorySeparatorChar>) separates the file path and the filename.</span></span>

<span data-ttu-id="2635e-144">다음은 UNC 경로의 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-144">The following are some examples of UNC paths:</span></span>

|<span data-ttu-id="2635e-145">경로</span><span class="sxs-lookup"><span data-stu-id="2635e-145">Path</span></span>  |<span data-ttu-id="2635e-146">설명</span><span class="sxs-lookup"><span data-stu-id="2635e-146">Description</span></span>  |
| -- | -- |
| `\\system07\C$\` | <span data-ttu-id="2635e-147">`system07`에 있는 `C:` 드라이브의 루트 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-147">The root directory of the `C:` drive on `system07`.</span></span> |
| `\\Server2\Share\Test\Foo.txt` | <span data-ttu-id="2635e-148">`\\Server2\Share` 볼륨의 Test 디렉터리에 있는 `Foo.txt` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-148">The `Foo.txt` file in the Test directory of the `\\Server2\Share` volume.</span></span>|

<span data-ttu-id="2635e-149">UNC 경로는 언제나 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-149">UNC paths must always be fully qualified.</span></span> <span data-ttu-id="2635e-150">이 경로는 상대 디렉터리 세그먼트(`.` 및 `..`)를 포함할 수 있지만 정규화된 경로의 일부이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-150">They can include relative directory segments (`.` and `..`), but these must be part of a fully qualified path.</span></span> <span data-ttu-id="2635e-151">UNC 경로를 드라이브 문자에 매핑해야만 상대 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-151">You can use relative paths only by mapping a UNC path to a drive letter.</span></span>

## <a name="dos-device-paths"></a><span data-ttu-id="2635e-152">DOS 디바이스 경로</span><span class="sxs-lookup"><span data-stu-id="2635e-152">DOS device paths</span></span>

<span data-ttu-id="2635e-153">Windows 운영 체제는 파일을 포함한 모든 리소스를 가리키는 통합된 개체 모델을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-153">The Windows operating system has a unified object model that points to all resources, including files.</span></span> <span data-ttu-id="2635e-154">이러한 개체 경로는 콘솔 창에서 액세스할 수 있으며 구형 DOS 및 UNC 경로를 매핑하는 대상인 기호 링크의 특수 폴더를 통해 Win32 레이어에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-154">These object paths are accessible from the console window and are exposed to the Win32 layer through a special folder of symbolic links that legacy DOS and UNC paths are mapped to.</span></span> <span data-ttu-id="2635e-155">이 특수 폴더는 다음 중 하나인 DOS 디바이스 경로 구문을 통해 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-155">This special folder is accessed via the DOS device path syntax, which is one of:</span></span>

`\\.\C:\Test\Foo.txt`
`\\?\C:\Test\Foo.txt`

<span data-ttu-id="2635e-156">드라이브 문자로 드라이브를 식별하는 것 외에, 볼륨 GUID로 볼륨을 식별할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-156">In addition to identifying a drive by its drive letter, you can identify a volume by using its volume GUID.</span></span> <span data-ttu-id="2635e-157">다음 양식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-157">This takes the form:</span></span>

`\\.\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`
`\\?\Volume{b75e2c83-0000-0000-0000-602f00000000}\Test\Foo.txt`

> [!NOTE]
> <span data-ttu-id="2635e-158">DOS 디바이스 경로 구문은 .NET Core 1.1 및 .NET Framework 4.6.2부터 Windows에서 실행하는 .NET 구현에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-158">DOS device path syntax is supported on .NET implementations running on Windows starting with .NET Core 1.1 and .NET Framework 4.6.2.</span></span>

<span data-ttu-id="2635e-159">DOS 디바이스 경로는 다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-159">The DOS device path consists of the following components:</span></span>

- <span data-ttu-id="2635e-160">경로를 DOS 디바이스 경로로 식별하는 디바이스 경로 지정자(`\\.\` 또는 `\\?\`).</span><span class="sxs-lookup"><span data-stu-id="2635e-160">The device path specifier (`\\.\` or `\\?\`), which identifies the path as a DOS device path.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2635e-161">`\\?\`는 모든 버전의 .NET Core 및 .NET 5 이상과 버전 4.6.2부터 .NET Framework에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-161">The `\\?\` is supported in all versions of .NET Core and .NET 5+ and in .NET Framework starting with version 4.6.2.</span></span>

- <span data-ttu-id="2635e-162">“실제” 디바이스 개체의 바로 가기 링크입니다(드라이브 이름의 경우 C:, 볼륨 GUID의 경우 Volume{b75e2c83-0000-0000-0000-602f00000000}).</span><span class="sxs-lookup"><span data-stu-id="2635e-162">A symbolic link to the "real" device object (C: in the case of a drive name, or Volume{b75e2c83-0000-0000-0000-602f00000000} in the case of a volume GUID).</span></span>

   <span data-ttu-id="2635e-163">디바이스 경로 지정자 뒤에 오는 DOS 디바이스 경로의 첫 번째 세그먼트는 볼륨 또는 드라이브를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-163">The first segment of the DOS device path after the device path specifier identifies the volume or drive.</span></span> <span data-ttu-id="2635e-164">(예를 들어 `\\?\C:\` 및 `\\.\BootPartition\`)</span><span class="sxs-lookup"><span data-stu-id="2635e-164">(For example, `\\?\C:\` and `\\.\BootPartition\`.)</span></span>

   <span data-ttu-id="2635e-165">호출된 UNC에 대한 특정 링크가 있습니다(당연히 `UNC`).</span><span class="sxs-lookup"><span data-stu-id="2635e-165">There is a specific link for UNCs that is called, not surprisingly, `UNC`.</span></span> <span data-ttu-id="2635e-166">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2635e-166">For example:</span></span>

  `\\.\UNC\Server\Share\Test\Foo.txt`
  `\\?\UNC\Server\Share\Test\Foo.txt`

    <span data-ttu-id="2635e-167">디바이스 UNC의 경우, 서버/공유 부분이 볼륨을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-167">For device UNCs, the server/share portion forms the volume.</span></span> <span data-ttu-id="2635e-168">예를 들어 `\\?\server1\e:\utilities\\filecomparer\`에서 서버/공유 부분은 `server1\utilities`입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-168">For example, in `\\?\server1\e:\utilities\\filecomparer\`, the server/share portion is `server1\utilities`.</span></span> <span data-ttu-id="2635e-169">이는 상대 디렉터리 경로를 사용하여 <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> 같은 메서드를 호출할 때 중요하며, 볼륨을 지나서 탐색하는 것은 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-169">This is significant when calling a method such as <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> with relative directory segments; it is never possible to navigate past the volume.</span></span>

<span data-ttu-id="2635e-170">DOS 디바이스 경로는 정의에 의해 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-170">DOS device paths are fully qualified by definition.</span></span> <span data-ttu-id="2635e-171">상대 디렉터리 세그먼트(`.` 및 `..`)는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-171">Relative directory segments (`.` and `..`) are not allowed.</span></span> <span data-ttu-id="2635e-172">현재 디렉터리는 해당 사용에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-172">Current directories never enter into their usage.</span></span>

## <a name="example-ways-to-refer-to-the-same-file"></a><span data-ttu-id="2635e-173">예: 동일한 파일을 참조하는 방법</span><span class="sxs-lookup"><span data-stu-id="2635e-173">Example: Ways to refer to the same file</span></span>

<span data-ttu-id="2635e-174">다음 예제는 <xref:System.IO> 네임스페이스에서 API를 사용할 때 파일을 참조할 수 있는 몇 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-174">The following example illustrates some of the ways in which you can refer to a file when using the APIs in the <xref:System.IO> namespace.</span></span> <span data-ttu-id="2635e-175">이 예제는 <xref:System.IO.FileInfo> 개체를 인스턴스화하고 해당 개체의 <xref:System.IO.FileInfo.Name> 및 <xref:System.IO.FileInfo.Length> 속성을 사용하여 파일 이름 및 파일의 길이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-175">The example instantiates a <xref:System.IO.FileInfo> object and uses its <xref:System.IO.FileInfo.Name> and <xref:System.IO.FileInfo.Length> properties to display the filename and the length of the file.</span></span>

[!code-csharp[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/cs/file-refs.cs)]
[!code-vb[referring-to-the-same-file](~/samples/snippets/standard/io/file-names/vb/file-refs.vb)]

## <a name="path-normalization"></a><span data-ttu-id="2635e-176">경로 표준화</span><span class="sxs-lookup"><span data-stu-id="2635e-176">Path normalization</span></span>

<span data-ttu-id="2635e-177">Windows API에 전달되는 거의 모든 경로는 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-177">Almost all paths passed to Windows APIs are normalized.</span></span> <span data-ttu-id="2635e-178">정규화 중에 Windows는 다음과 같은 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-178">During normalization, Windows performs the following steps:</span></span>

- <span data-ttu-id="2635e-179">파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-179">Identifies the path.</span></span>
- <span data-ttu-id="2635e-180">현재 디렉터리를 부분적으로 정규화된 (상대) 경로에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-180">Applies the current directory to partially qualified (relative) paths.</span></span>
- <span data-ttu-id="2635e-181">구성 요소 및 디렉터리 구분 기호를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-181">Canonicalizes component and directory separators.</span></span>
- <span data-ttu-id="2635e-182">상대 디렉터리 구성 요소(현재 디렉터리의 경우 `.` 및 부모 디렉터리의 경우 `..`)를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-182">Evaluates relative directory components (`.` for the current directory and `..` for the parent directory).</span></span>
- <span data-ttu-id="2635e-183">특정 문자를 잘라냅니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-183">Trims certain characters.</span></span>

<span data-ttu-id="2635e-184">이 정규화는 암시적으로 일어나지만 [GetFullPathName() 함수](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) 호출을 래핑하는 <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> 메서드를 호출하여 명시적으로 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-184">This normalization happens implicitly, but you can do it explicitly by calling the <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType> method, which wraps a call to the  [GetFullPathName() function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).</span></span> <span data-ttu-id="2635e-185">또한 P/Invoke를 사용하여 Windows [GetFullPathName() 함수](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)를 직접 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-185">You can also call the Windows [GetFullPathName() function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) directly using P/Invoke.</span></span>

### <a name="identify-the-path"></a><span data-ttu-id="2635e-186">경로 확인</span><span class="sxs-lookup"><span data-stu-id="2635e-186">Identify the path</span></span>

<span data-ttu-id="2635e-187">경로 정규화의 첫 번째 단계는 경로의 형식 식별입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-187">The first step in path normalization is identifying the type of path.</span></span> <span data-ttu-id="2635e-188">경로는 몇 가지 범주 중 하나에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-188">Paths fall into one of a few categories:</span></span>

- <span data-ttu-id="2635e-189">디바이스 경로인 경우. 즉, 구분 기호 두 개와 물음표 또는 마침표(`\\?` 또는 `\\.`)로 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-189">They are device paths; that is, they begin with two separators and a question mark or period (`\\?` or `\\.`).</span></span>
- <span data-ttu-id="2635e-190">UNC 경로인 경우. 즉, 물음표 또는 마침표 없이 구분 기호 두 개로 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-190">They are UNC paths; that is, they begin with two separators without a question mark or period.</span></span>
- <span data-ttu-id="2635e-191">정규화된 DOS 경로인 경우. 즉, 드라이브 문자, 볼륨 구분 기호 및 구성 요소 구분 기호(`C:\`)로 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-191">They are fully qualified DOS paths; that is, they begin with a drive letter, a volume separator, and a component separator (`C:\`).</span></span>
- <span data-ttu-id="2635e-192">구형 디바이스(`CON`, `LPT1`)를 지정하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-192">They designate a legacy device (`CON`, `LPT1`).</span></span>
- <span data-ttu-id="2635e-193">현재 드라이브의 루트를 기준으로 하는 경우. 즉, 단일 구성 요소 구분 기호(`\`)로 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-193">They are relative to the root of the current drive; that is, they begin with a single component separator (`\`).</span></span>
- <span data-ttu-id="2635e-194">지정한 드라이브의 현재 디렉터리를 기준으로 하는 경우. 즉, 드라이브 문자, 볼륨 구분 기호로 시작하고 구성 요소 구분 기호(`C:`)가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-194">They are relative to the current directory of a specified drive; that is, they begin with a drive letter, a volume separator, and no component separator (`C:`).</span></span>
- <span data-ttu-id="2635e-195">현재 디렉터리를 기준으로 하는 경우. 즉, 다른 요소(`temp\testfile.txt`)로 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2635e-195">They are relative to the current directory; that is, they begin with anything else (`temp\testfile.txt`).</span></span>

<span data-ttu-id="2635e-196">경로 형식은 현재 디렉터리가 일정한 방법으로 적용되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-196">The type of the path determines whether or not a current directory is applied in some way.</span></span> <span data-ttu-id="2635e-197">경로의 "루트"가 무엇인지도 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-197">It also determines what the "root" of the path is.</span></span>

### <a name="handle-legacy-devices"></a><span data-ttu-id="2635e-198">구형 디바이스 처리</span><span class="sxs-lookup"><span data-stu-id="2635e-198">Handle legacy devices</span></span>

<span data-ttu-id="2635e-199">경로가 `CON`, `COM1` 또는 `LPT1` 같은 구형 DOS 디바이스인 경우 앞에 `\\.\`를 덧붙여 디바이스 경로로 변환한 다음, 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-199">If the path is a legacy DOS device such as `CON`, `COM1`, or `LPT1`, it is converted into a device path by prepending `\\.\` and returned.</span></span>

<span data-ttu-id="2635e-200">구형 디바이스 이름으로 시작하는 경로는 언제나 <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType> 메서드에 의해 구형 디바이스로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-200">A path that begins with a legacy device name is always interpreted as a legacy device by the <xref:System.IO.Path.GetFullPath(System.String)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2635e-201">예를 들어 `CON.TXT`에 대한 DOS 디바이스 경로는 `\\.\CON`이며, `COM1.TXT\file1.txt`에 대한 DOS 디바이스 경로는 `\\.\COM1`입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-201">For example, the DOS device path for `CON.TXT` is `\\.\CON`, and the DOS device path for `COM1.TXT\file1.txt` is `\\.\COM1`.</span></span>

### <a name="apply-the-current-directory"></a><span data-ttu-id="2635e-202">현재 디렉터리 적용</span><span class="sxs-lookup"><span data-stu-id="2635e-202">Apply the current directory</span></span>

<span data-ttu-id="2635e-203">경로가 정규화되지 않은 경우 Windows는 현재 디렉터리를 해당 경로에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-203">If a path isn't fully qualified, Windows applies the current directory to it.</span></span> <span data-ttu-id="2635e-204">UNC 및 디바이스 경로에는 현재 디렉터리가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-204">UNCs and device paths do not have the current directory applied.</span></span> <span data-ttu-id="2635e-205">구분 기호를 포함하는 전체 드라이브 `C:\`에도 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-205">Neither does a full drive with separator `C:\`.</span></span>

<span data-ttu-id="2635e-206">경로가 단일 구성 요소 구분 기호로 시작하는 경우 현재 디렉터리의 드라이브를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-206">If the path starts with a single component separator, the drive from the current directory is applied.</span></span> <span data-ttu-id="2635e-207">예를 들어 파일 경로가 `\utilities`이고 현재 디렉터리가 `C:\temp\`인 경우, 정규화하면 `C:\utilities`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-207">For example, if the file path is `\utilities` and the current directory is `C:\temp\`, normalization produces `C:\utilities`.</span></span>

<span data-ttu-id="2635e-208">경로가 드라이브 문자, 볼륨 구분 기호로 시작하고 구성 요소 구분 기호가 없는 경우, 지정한 드라이브의 명령 셸에서 설정한 마지막 현재 디렉터리를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-208">If the path starts with a drive letter, volume separator, and no component separator, the last current directory set from the command shell for the specified drive is applied.</span></span> <span data-ttu-id="2635e-209">마지막 현재 디렉터리가 설정되지 않은 경우 드라이브만 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-209">If the last current directory was not set, the drive alone is applied.</span></span> <span data-ttu-id="2635e-210">예를 들어 파일 경로가 `D:sources`이고, 현재 디렉터리가 `C:\Documents\`이고, 드라이브 D:의 마지막 현재 디렉터리가 `D:\sources\`이면 결과는 `D:\sources\sources`입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-210">For example, if the file path is `D:sources`, the current directory is `C:\Documents\`, and the last current directory on drive D: was `D:\sources\`, the result is `D:\sources\sources`.</span></span> <span data-ttu-id="2635e-211">이러한 "드라이브 상대" 경로는 프로그램 및 스크립트 논리 오류의 일반적인 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-211">These "drive relative" paths are a common source of program and script logic errors.</span></span> <span data-ttu-id="2635e-212">문자와 콜론으로 시작하는 경로가 상대 경로가 아니라고 가정하는 것은 명백히 틀린 가정입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-212">Assuming that a path beginning with a letter and a colon isn't relative is obviously not correct.</span></span>

<span data-ttu-id="2635e-213">경로가 구분 기호 이외의 요소로 시작하는 경우 현재 드라이브 및 현재 디렉터리를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-213">If the path starts with something other than a separator, the current drive and current directory are applied.</span></span> <span data-ttu-id="2635e-214">예를 들어 경로가 `filecompare`이고 현재 디렉터리가 `C:\utilities\`인 경우, 결과는 `C:\utilities\filecompare\`입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-214">For example, if the path is `filecompare` and the current directory is `C:\utilities\`, the result is `C:\utilities\filecompare\`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2635e-215">현재 디렉터리는 프로세스에 따른 설정이므로 상대 경로는 멀티스레드 애플리케이션(즉, 대부분의 애플리케이션)에서 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-215">Relative paths are dangerous in multithreaded applications (that is, most applications) because the current directory is a per-process setting.</span></span> <span data-ttu-id="2635e-216">스레드는 현재 디렉터리를 언제든지 변경할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-216">Any thread can change the current directory at any time.</span></span> <span data-ttu-id="2635e-217">.NET Core 2.1부터 <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> 메서드를 호출하여 상대 경로 및 기본 경로(현재 디렉터리)에서 확인하려는 기준이 되는 절대 경로를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-217">Starting with .NET Core 2.1, you can call the <xref:System.IO.Path.GetFullPath(System.String,System.String)?displayProperty=nameWithType> method to get an absolute path from a relative path and the base path (the current directory) that you want to resolve it against.</span></span>

### <a name="canonicalize-separators"></a><span data-ttu-id="2635e-218">구분 기호 정규화</span><span class="sxs-lookup"><span data-stu-id="2635e-218">Canonicalize separators</span></span>

<span data-ttu-id="2635e-219">모든 슬래시(`/`)는 표준 Windows 구분 기호인 백슬래시(`\`)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-219">All forward slashes (`/`) are converted into the standard Windows separator, the back slash (`\`).</span></span> <span data-ttu-id="2635e-220">슬래시가 존재하는 경우 첫 번째 슬래시 다음에 오는 일련의 슬래시를 단일 슬래시로 축소합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-220">If they are present, a series of slashes that follow the first two slashes are collapsed into a single slash.</span></span>

### <a name="evaluate-relative-components"></a><span data-ttu-id="2635e-221">상대 구성 요소 평가</span><span class="sxs-lookup"><span data-stu-id="2635e-221">Evaluate relative components</span></span>

<span data-ttu-id="2635e-222">경로가 처리될 때 단일 또는 이중 마침표(`.` 또는 `..`)로 구성된 구성 요소 또는 세그먼트를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-222">As the path is processed, any components or segments that are composed of a single or a double period (`.` or `..`) are evaluated:</span></span>

- <span data-ttu-id="2635e-223">단일 마침표의 경우, 현재 디렉터리를 가리키므로 현재 세그먼트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-223">For a single period, the current segment is removed, since it refers to the current directory.</span></span>

- <span data-ttu-id="2635e-224">이중 마침표의 경우, 부모 디렉터리를 가리키므로 현재 세그먼트 및 부모 세그먼트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-224">For a double period, the current segment and the parent segment are removed, since the double period refers to the parent directory.</span></span>

   <span data-ttu-id="2635e-225">부모 디렉터리는 경로의 루트를 지나가지 않는 경우에만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-225">Parent directories are only removed if they aren't past the root of the path.</span></span> <span data-ttu-id="2635e-226">경로의 루트는 경로의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-226">The root of the path depends on the type of path.</span></span> <span data-ttu-id="2635e-227">즉, DOS 경로의 경우 드라이브(`C:\`)이고, UNC(`\\Server\Share`) 경로의 경우 서버/공유이며, 디바이스 경로(`\\?\` 또는 `\\.\`)의 경우 디바이스 경로 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-227">It is the drive (`C:\`) for DOS paths, the server/share for UNCs (`\\Server\Share`), and the device path prefix for device paths (`\\?\` or `\\.\`).</span></span>

### <a name="trim-characters"></a><span data-ttu-id="2635e-228">문자 자르기</span><span class="sxs-lookup"><span data-stu-id="2635e-228">Trim characters</span></span>

<span data-ttu-id="2635e-229">앞에서 제거한 일련의 구분 기호 및 상대 세그먼트와 함께 일부 추가 문자를 정규화 중에 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-229">Along with the runs of separators and relative segments removed earlier, some additional characters are removed during normalization:</span></span>

- <span data-ttu-id="2635e-230">세그먼트가 단일 마침표로 끝나는 경우 해당 마침표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-230">If a segment ends in a single period, that period is removed.</span></span> <span data-ttu-id="2635e-231">(단일 또는 이중 마침표의 세그먼트는 이전 단계에서 정규화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-231">(A segment of a single or double period is normalized in the previous step.</span></span> <span data-ttu-id="2635e-232">마침표 3개 이상의 세그먼트는 정규화되지 않으며 실제로 유효한 파일/디렉터리 이름입니다.)</span><span class="sxs-lookup"><span data-stu-id="2635e-232">A segment of three or more periods is not normalized and is actually a valid file/directory name.)</span></span>

- <span data-ttu-id="2635e-233">경로가 구분 기호로 끝나지 않는 경우 모든 후행 마침표와 공백(U+0020)을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-233">If the path doesn't end in a separator, all trailing periods and spaces (U+0020) are removed.</span></span> <span data-ttu-id="2635e-234">마지막 세그먼트가 단순히 단일 또는 이중 마침표인 경우, 이는 위의 상대 구성 요소 규칙에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-234">If the last segment is simply a single or double period, it falls under the relative components rule above.</span></span>

   <span data-ttu-id="2635e-235">이 규칙은 공백 뒤에 후행 구분 기호를 추가하면 후행 공백을 사용하여 디렉터리 이름을 만들 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-235">This rule means that you can create a directory name with a trailing space by adding a trailing separator after the space.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2635e-236">후행 공백을 사용하여 디렉터리 또는 파일 이름을 만들지 **말아야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-236">You should **never** create a directory or filename with a trailing space.</span></span> <span data-ttu-id="2635e-237">후행 공백은 디렉터리 액세스를 어렵게 또는 불가능하게 만들 수 있으며, 해당 이름이 후행 공백을 포함하는 디렉터리 또는 파일의 처리를 시도할 때 흔히 애플리케이션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-237">Trailing spaces can make it difficult or impossible to access a directory, and applications commonly fail when attempting to handle directories or files whose names include trailing spaces.</span></span>

## <a name="skip-normalization"></a><span data-ttu-id="2635e-238">건너뛰기 정규화</span><span class="sxs-lookup"><span data-stu-id="2635e-238">Skip normalization</span></span>

<span data-ttu-id="2635e-239">일반적으로 Windows API에 전달되는 경로는 (결과적으로) [GetFullPathName 함수](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)에 전달되고 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-239">Normally, any path passed to a Windows API is (effectively) passed to the [GetFullPathName function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) and normalized.</span></span> <span data-ttu-id="2635e-240">여기에 중요한 한 가지 예외가 있는데, 바로 마침표 대신에 물음표로 시작하는 디바이스 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-240">There is one important exception: a device path that begins with a question mark instead of a period.</span></span> <span data-ttu-id="2635e-241">경로는 `\\?\`로 시작하지 않는 한(canonical 백슬래시 사용에 주의) 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-241">Unless the path starts exactly with `\\?\` (note the use of the canonical backslash), it is normalized.</span></span>

<span data-ttu-id="2635e-242">정규화를 건너뛰려는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="2635e-242">Why would you want to skip normalization?</span></span> <span data-ttu-id="2635e-243">세 가지 중요한 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-243">There are three major reasons:</span></span>

1. <span data-ttu-id="2635e-244">일반적으로 사용할 수 없지만 올바른 경로에 액세스.</span><span class="sxs-lookup"><span data-stu-id="2635e-244">To get access to paths that are normally unavailable but are legal.</span></span> <span data-ttu-id="2635e-245">예를 들어 `hidden.`이라는 파일 또는 디렉터리는 다른 방법으로 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-245">A file or directory called `hidden.`, for example, is impossible to access in any other way.</span></span>

1. <span data-ttu-id="2635e-246">이미 일반화된 경우 일반화를 건너뛰어서 성능을 개선.</span><span class="sxs-lookup"><span data-stu-id="2635e-246">To improve performance by skipping normalization if you've already normalized.</span></span>

1. <span data-ttu-id="2635e-247">.NET Framework에 한하여, `MAX_PATH`를 건너뛰려면 경로 길이가 259문자보다 더 큰 경로를 허용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-247">On .NET Framework only, to skip the `MAX_PATH` check for path length to allow for paths that are greater than 259 characters.</span></span> <span data-ttu-id="2635e-248">대부분의 API는 이 크기를 허용하지만, 몇 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-248">Most APIs allow this, with some exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="2635e-249">.NET Core 및 .NET 5 이상은 암시적으로 긴 경로를 처리하며 `MAX_PATH` 검사를 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-249">.NET Core and .NET 5+ handles long paths implicitly and does not perform a `MAX_PATH` check.</span></span> <span data-ttu-id="2635e-250">`MAX_PATH` 검사는 .NET Framework에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-250">The `MAX_PATH` check applies only to .NET Framework.</span></span>

<span data-ttu-id="2635e-251">정규화 및 최대 경로 검사를 건너뛰는 것은 두 디바이스 경로 구문 간에만 차이점이 있으며, 다른 면에서는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-251">Skipping normalization and max path checks is the only difference between the two device path syntaxes; they are otherwise identical.</span></span> <span data-ttu-id="2635e-252">정규화를 건너뛸 때에는 "일반적인" 애플리케이션이 처리하기 어려운 경로를 생성하기 쉽기 때문에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-252">Be careful with skipping normalization, since you can easily create paths that are difficult for "normal" applications to deal with.</span></span>

<span data-ttu-id="2635e-253">`\\?\`로 시작하는 경로는 [GetFullPathName 함수](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)에 명시적으로 전달하더라도 여전히 정규화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-253">Paths that start with `\\?\` are still normalized if you explicitly pass them to the [GetFullPathName function](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).</span></span>

<span data-ttu-id="2635e-254">`MAX_PATH` 문자보다 큰 경로는 `\\?\` 없이 [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea)에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-254">You can pass paths of more than `MAX_PATH` characters to [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) without `\\?\`.</span></span> <span data-ttu-id="2635e-255">이는 Windows에서 처리할 수 있는 최대 문자열 크기까지 임의 길이의 경로를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-255">It supports arbitrary length paths up to the maximum string size that Windows can handle.</span></span>

## <a name="case-and-the-windows-file-system"></a><span data-ttu-id="2635e-256">대/소문자 및 Windows 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="2635e-256">Case and the Windows file system</span></span>

<span data-ttu-id="2635e-257">Windows 이외의 사용자와 개발자가 혼동을 일으키는 Windows 파일 시스템의 특징은 경로 및 디렉터리 이름이 대/소문자를 구분하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-257">A peculiarity of the Windows file system that non-Windows users and developers find confusing is that path and directory names are case-insensitive.</span></span> <span data-ttu-id="2635e-258">즉, 디렉터리 및 파일 이름은 생성될 때 사용하는 문자열의 대/소문자를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-258">That is, directory and file names reflect the casing of the strings used when they are created.</span></span> <span data-ttu-id="2635e-259">예를 들어 다음 메서드 호출은</span><span class="sxs-lookup"><span data-stu-id="2635e-259">For example, the method call</span></span>

```csharp
Directory.Create("TeStDiReCtOrY");
```

```vb
Directory.Create("TeStDiReCtOrY")
```

<span data-ttu-id="2635e-260">TeStDiReCtOrY라는 디렉터리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-260">creates a directory named TeStDiReCtOrY.</span></span> <span data-ttu-id="2635e-261">해당 대/소문자를 변경하기 위해 디렉터리 또는 파일을 이름 변경하는 경우, 디렉터리 또는 파일 이름은 이름 변경할 당시에 사용한 문자열의 대/소문자를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-261">If you rename a directory or file to change its case, the directory or file name reflects the case of the string used when you rename it.</span></span> <span data-ttu-id="2635e-262">예를 들어 다음 코드는 test.txt라는 파일을 Test.txt로 이름 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-262">For example, the following code renames a file named test.txt to Test.txt:</span></span>

[!code-csharp[case-and-renaming](~/samples/snippets/standard/io/file-names/cs/rename.cs)]
[!code-vb[case-and-renaming](~/samples/snippets/standard/io/file-names/vb/rename.vb)]

<span data-ttu-id="2635e-263">그러나 디렉터리 및 파일 이름 비교는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-263">However, directory and file name comparisons are case-insensitive.</span></span> <span data-ttu-id="2635e-264">"test.txt"라는 파일을 검색하는 경우, .NET 파일 시스템 API는 비교 시 대/소문자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-264">If you search for a file named "test.txt", .NET file system APIs ignore case in the comparison.</span></span> <span data-ttu-id="2635e-265">"Test.txt", "TEST.TXT", "test.TXT" 및 다른 어떤 대/소문자 조합도 "test.txt"와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="2635e-265">"Test.txt", "TEST.TXT", "test.TXT", and any other combination of uppercase and lowercase letters will match "test.txt".</span></span>
