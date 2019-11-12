---
title: '완화: 제품 버전 관리'
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
ms.openlocfilehash: 64a68d2b79a0a3ccdd806949ffd6cb3760974390
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457809"
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="e333c-102">완화: 제품 버전 관리</span><span class="sxs-lookup"><span data-stu-id="e333c-102">Mitigation: Product Versioning</span></span>

<span data-ttu-id="e333c-103">.NET Framework 4.6 이상에서, 제품 버전 관리가 .NET Framework(.NET Framework 4, 4.5, 4.5.1 및 4.5.2)의 이전 릴리스에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-103">In the .NET Framework 4.6 and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>

## <a name="product-versioning-changes"></a><span data-ttu-id="e333c-104">제품 버전 관리 변경 내용</span><span class="sxs-lookup"><span data-stu-id="e333c-104">Product versioning changes</span></span>

<span data-ttu-id="e333c-105">자세한 변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-105">The following are the detailed changes:</span></span>

- <span data-ttu-id="e333c-106">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`키에서 `Version` 항목의 값은 .NET Framework 4.6 및 해당 포인트 릴리스에 대해 `4.6.`*xxxxx*로, .NET Framework 4.7에 대해 `4.7.`*xxxxx*로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-106">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="e333c-107">.NET Framework 4.5, 4.5.1 및 4.5.2에서는 `4.5.`*xxxxx* 형식이었습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-107">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>

- <span data-ttu-id="e333c-108">.NET Framework 파일에 대한 파일 및 제품 버전 관리는 이전 버전 관리 체계의 `4.0.30319.x`에서 .NET Framework 4.6 및 해당 포인트 릴리스에 대해 `4.6.X.0`로, .NET Framework 4.7 및 해당 포인트에 대해 `4.7.X.0`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-108">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="e333c-109">파일을 마우스 오른쪽 단추로 클릭한 후 파일의 **속성**을 보면 이러한 새 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-109">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>

- <span data-ttu-id="e333c-110">관리되는 어셈블리의 <xref:System.Reflection.AssemblyFileVersionAttribute> 및 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 특성은 .NET Framework 4.6 및 해당 포인트 릴리스의 경우 `4.6.X.0` 형식, 그리고 .NET Framework 4.7의 경우에는 `4.7.X.0` 형식의 <xref:System.Version> 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-110">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>

- <span data-ttu-id="e333c-111">.NET Framework 4.6부터 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 속성은 최종 버전 문자열 `4.0.30319.42000`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-111">Starting with .NET Framework 4.6, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="e333c-112">.NET Framework 4, 4.5, 4.5.1 및 4.5.2에서는 `xxxxx`가 42000보다 작은 `4.0.30319.xxxxx` 형식의 버전 문자열을 반환합니다(예: "4.0.30319.18010").</span><span class="sxs-lookup"><span data-stu-id="e333c-112">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` where `xxxxx` is less than 42000 (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="e333c-113"><xref:System.Environment.Version%2A?displayProperty=nameWithType> 속성에서 새 종속성을 취하는 애플리케이션 코드는 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-113">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>

### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="e333c-114">제품 버전 관리 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="e333c-114">Handling the product versioning changes</span></span>

<span data-ttu-id="e333c-115">일반적으로 애플리케이션은 .NET Framework 및 설치 디렉터리 검색의 런타임 버전과 같은 항목 검색을 위한 권장 기술에 의존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-115">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>

- <span data-ttu-id="e333c-116">.NET Framework의 런타임 버전을 검색하려면 [방법: 설치된 .NET Framework 버전 확인](how-to-determine-which-versions-are-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e333c-116">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](how-to-determine-which-versions-are-installed.md).</span></span>

- <span data-ttu-id="e333c-117">.NET Framework의 설치 경로를 확인하려면`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 키의 `InstallPath` 항목 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-117">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e333c-118">하위 키 이름은 `.NET Framework Setup`이 아니라 `NET Framework Setup`입니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-118">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>

- <span data-ttu-id="e333c-119">.NET Framework 공용 언어 런타임에 대한 디렉터리 경로를 확인하려면 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-119">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="e333c-120">CLR 버전을 알아보려면 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-120">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="e333c-121">.NET Framework 4 및 해당 지점 릴리스(.NET Framework 4.5, 4.5.1, 4.5.2 및 .NET Framework 4.6, 4.6.1, 4.6.2 및 4.7)의 경우 문자열 `v4.0.30319`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e333c-121">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and .NET Framework 4.6, 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e333c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e333c-122">See also</span></span>

- [<span data-ttu-id="e333c-123">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="e333c-123">Application compatibility</span></span>](application-compatibility.md)
