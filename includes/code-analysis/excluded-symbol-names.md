---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366858"
---
### <a name="exclude-specific-symbols"></a><span data-ttu-id="1d78c-101">특정 기호 제외</span><span class="sxs-lookup"><span data-stu-id="1d78c-101">Exclude specific symbols</span></span>

<span data-ttu-id="1d78c-102">분석에서 형식 및 메서드와 같은 특정 기호를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-102">You can exclude specific symbols, such as types and methods, from analysis.</span></span> <span data-ttu-id="1d78c-103">예를 들어 이름이 인 형식 내의 코드에서 규칙이 실행 되지 않도록 지정 하려면 `MyType` 프로젝트의 *editorconfig* 파일에 다음 키-값 쌍을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-103">For example, to specify that the rule should not run on any code within types named `MyType`, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

<span data-ttu-id="1d78c-104">옵션 값의 허용 되는 기호 이름 형식 (로 구분 `|` ):</span><span class="sxs-lookup"><span data-stu-id="1d78c-104">Allowed symbol name formats in the option value (separated by `|`):</span></span>

- <span data-ttu-id="1d78c-105">기호 이름만 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 기호 포함).</span><span class="sxs-lookup"><span data-stu-id="1d78c-105">Symbol name only (includes all symbols with the name, regardless of the containing type or namespace).</span></span>
- <span data-ttu-id="1d78c-106">기호의 [문서 ID 형식](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)에 대 한 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-106">Fully qualified names in the symbol's [documentation ID format](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings).</span></span> <span data-ttu-id="1d78c-107">각 기호 이름에는 `M:` 메서드, `T:` 형식 및 네임 스페이스에 대 한 기호 종류 접두사가 필요 합니다 `N:` .</span><span class="sxs-lookup"><span data-stu-id="1d78c-107">Each symbol name requires a symbol-kind prefix, such as `M:` for methods, `T:` for types, and `N:` for namespaces.</span></span>
- <span data-ttu-id="1d78c-108">`.ctor` 생성자의 경우이 고, `.cctor` 정적 생성자의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-108">`.ctor` for constructors and `.cctor` for static constructors.</span></span>

<span data-ttu-id="1d78c-109">예제:</span><span class="sxs-lookup"><span data-stu-id="1d78c-109">Examples:</span></span>

| <span data-ttu-id="1d78c-110">옵션 값</span><span class="sxs-lookup"><span data-stu-id="1d78c-110">Option Value</span></span> | <span data-ttu-id="1d78c-111">요약</span><span class="sxs-lookup"><span data-stu-id="1d78c-111">Summary</span></span> |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | <span data-ttu-id="1d78c-112">이라는 모든 기호와 일치 `MyType` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-112">Matches all symbols named `MyType`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | <span data-ttu-id="1d78c-113">또는 중 하나에 해당 하는 모든 기호 `MyType1` 를 찾습니다 `MyType2` .</span><span class="sxs-lookup"><span data-stu-id="1d78c-113">Matches all symbols named either `MyType1` or `MyType2`.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | <span data-ttu-id="1d78c-114">지정 된 정규화 된 시그니처와 특정 메서드를 일치 시킵니다 `MyMethod` .</span><span class="sxs-lookup"><span data-stu-id="1d78c-114">Matches specific method `MyMethod` with the specified fully qualified signature.</span></span> |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | <span data-ttu-id="1d78c-115">특정 메서드와 `MyMethod1` 해당 하 `MyMethod2` 는 정규화 된 시그니처를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1d78c-115">Matches specific methods `MyMethod1` and `MyMethod2` with the respective fully qualified signatures.</span></span> |
