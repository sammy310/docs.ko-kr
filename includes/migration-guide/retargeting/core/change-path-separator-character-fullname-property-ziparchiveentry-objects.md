---
ms.openlocfilehash: 148312743dd274728b178951548889dc3a680528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614695"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="e4a7b-101">ZipArchiveEntry 개체의 FullName 속성에서 경로 구분 기호 문자 변경</span><span class="sxs-lookup"><span data-stu-id="e4a7b-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

#### <a name="details"></a><span data-ttu-id="e4a7b-102">설명</span><span class="sxs-lookup"><span data-stu-id="e4a7b-102">Details</span></span>

<span data-ttu-id="e4a7b-103">.NET Framework 4.6.1 이상 버전을 대상으로 하는 앱의 경우 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> 메서드의 오버로드를 통해 생성된 <xref:System.IO.Compression.ZipArchiveEntry> 개체의 <xref:System.IO.Compression.ZipArchiveEntry.FullName> 속성에서 경로 구분 기호 문자가 백슬래시(\")에서 슬래시(/)로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash ("\") to a forward slash ("/") in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="e4a7b-104">이 변경으로 인해 .NET 구현은 [.ZIP 파일 형식 사양](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)의 섹션 4.4.17.1과 일치하게 되고 비 Windows 시스템에서.ZIP 아카이브의 압축이 풀리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span><br /><span data-ttu-id="e4a7b-105">Macintosh와 같은 비 Windows 운영 체제에서 이전 버전의 .NET Framework를 대상으로 하는 앱이 생성한 zip 파일의 압축을 풀면 디렉터리 구조가 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-105">Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="e4a7b-106">예를 들어 Macintosh에서는 해당 파일 이름이 디렉터리 경로, 백슬래시("") 문자 및 파일 이름으로 연결된 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-106">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("") characters, and the filename.</span></span> <span data-ttu-id="e4a7b-107">결과적으로 압축을 푼 파일의 디렉터리 구조는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-107">As a result, the directory structure of decompressed files is not preserved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e4a7b-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e4a7b-108">Suggestion</span></span>

<span data-ttu-id="e4a7b-109">.NET Framework <xref:System.IO?displayProperty=nameWithType> 네임스페이스의 API는 슬래시("/") 또는 백슬래시("\"")를 경로 구분 기호 문자로 원활하게 처리할 수 있으므로 이러한 API에 의해 Windows 운영 체제에서 압축 해제된 .ZIP 파일에 이러한 변경이 미치는 영향은 최소로 유지될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-109">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a forward slash ("/") or a backslash ("\") as the path separator character.</span></span><br /><span data-ttu-id="e4a7b-110">이 변경을 원치 않을 경우 애플리케이션 구성 파일의 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-110">If this change is undesirable, you can opt out of it by adding a configuration setting to the [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="e4a7b-111">다음 예제에서는 `<runtime>` 섹션 및 `Switch.System.IO.Compression.ZipFile.UseBackslash` 옵트아웃 스위치를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-111">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

<span data-ttu-id="e4a7b-112">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.1 이상 버전에서 실행되는 앱은 애플리케이션 구성 파일의 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 이 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-112">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="e4a7b-113">다음에서는 `<runtime>` 섹션 및 `Switch.System.IO.Compression.ZipFile.UseBackslash` 옵트인 스위치를 모두 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4a7b-113">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| <span data-ttu-id="e4a7b-114">이름</span><span class="sxs-lookup"><span data-stu-id="e4a7b-114">Name</span></span>    | <span data-ttu-id="e4a7b-115">값</span><span class="sxs-lookup"><span data-stu-id="e4a7b-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e4a7b-116">Scope</span><span class="sxs-lookup"><span data-stu-id="e4a7b-116">Scope</span></span>   | <span data-ttu-id="e4a7b-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e4a7b-117">Edge</span></span>        |
| <span data-ttu-id="e4a7b-118">버전</span><span class="sxs-lookup"><span data-stu-id="e4a7b-118">Version</span></span> | <span data-ttu-id="e4a7b-119">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e4a7b-119">4.6.1</span></span>       |
| <span data-ttu-id="e4a7b-120">형식</span><span class="sxs-lookup"><span data-stu-id="e4a7b-120">Type</span></span>    | <span data-ttu-id="e4a7b-121">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e4a7b-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e4a7b-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e4a7b-122">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
