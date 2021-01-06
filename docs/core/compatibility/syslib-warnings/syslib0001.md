---
title: SYSLIB0001 경고
description: 컴파일 시간 경고 SYSLIB0001을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 6c4b6a2f41e9dc044ef76bb5a53a4a54a44bca5a
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596381"
---
# <a name="syslib0001-the-utf-7-encoding-is-insecure"></a><span data-ttu-id="3ee9b-103">SYSLIB0001: UTF-7 인코딩이 안전하지 않음</span><span class="sxs-lookup"><span data-stu-id="3ee9b-103">SYSLIB0001: The UTF-7 encoding is insecure</span></span>

<span data-ttu-id="3ee9b-104">UTF-7 인코딩은 더 이상 애플리케이션에서 광범위하게 사용되지 않으며, 이제 많은 사양에서는 교환에 [사용을 금지](https://security.stackexchange.com/a/68609/3573)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="3ee9b-105">간혹 UTF-7로 인코딩된 데이터를 기대하지 않는 애플리케이션에서 [공격 벡터로 사용](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7)되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="3ee9b-106">오류 검색 기능이 제공되지 않기 때문에 Microsoft는 <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>을 사용하지 않도록 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="3ee9b-107">따라서 다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-107">Consequently, the following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="3ee9b-108">이러한 API를 사용하면 컴파일 시간에 `SYSLIB0001` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-108">Use of these APIs generates warning `SYSLIB0001` at compile time.</span></span>

- <span data-ttu-id="3ee9b-109"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 속성</span><span class="sxs-lookup"><span data-stu-id="3ee9b-109"><xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property</span></span>
- <span data-ttu-id="3ee9b-110"><xref:System.Text.UTF7Encoding.%23ctor%2A> 생성자</span><span class="sxs-lookup"><span data-stu-id="3ee9b-110"><xref:System.Text.UTF7Encoding.%23ctor%2A> constructors</span></span>

## <a name="workarounds"></a><span data-ttu-id="3ee9b-111">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3ee9b-111">Workarounds</span></span>

- <span data-ttu-id="3ee9b-112">사용자 고유의 프로토콜 또는 파일 형식에서 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> 또는 <xref:System.Text.UTF7Encoding>을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="3ee9b-112">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="3ee9b-113"><xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> 또는 <xref:System.Text.UTF8Encoding>을 사용하도록 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-113">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="3ee9b-114">UTF-8은 업계 표준이며 광범위한 언어, 운영 체제 및 런타임에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-114">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="3ee9b-115">UTF-8을 사용하면 나중에 코드를 더 쉽게 유지 관리할 수 있으며, 나머지 에코시스템과 상호 운용이 더 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-115">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="3ee9b-116"><xref:System.Text.Encoding> 인스턴스를 <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>과 비교하는 경우:</span><span class="sxs-lookup"><span data-stu-id="3ee9b-116">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="3ee9b-117">대신, 잘 알려진 UTF-7 코드 페이지 `65000`에 대해 검사를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-117">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="3ee9b-118">이 코드 페이지와 비교하여 경고를 방지하고, 다른 사용자가 `new UTF7Encoding()`를 호출했거나 형식이 서브클래싱된 경우와 같은 일부 특수한 사례를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee9b-118">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="3ee9b-119">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3ee9b-119">See also</span></span>

- [<span data-ttu-id="3ee9b-120">UTF-7 코드 경로가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="3ee9b-120">UTF-7 code paths are obsolete</span></span>](../core-libraries/5.0/utf-7-code-paths-obsolete.md)
