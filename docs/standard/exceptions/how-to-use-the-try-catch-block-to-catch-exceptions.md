---
title: '방법: Try-Catch 블록을 사용하여 예외 catch'
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 5a9218d394b76e897f4263708a10f1bc895ad4e1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708468"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="9e6dd-102">try/catch 블록을 사용하여 예외를 catch하는 방법</span><span class="sxs-lookup"><span data-stu-id="9e6dd-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="9e6dd-103">예외를 발생시키거나 throw할 수 있는 모든 코드 문을 `try` 블록에 배치하고, 예외를 처리하는 데 사용되는 명령문을 `try` 블록 아래에 있는 하나 이상의 `catch` 블록에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-103">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="9e6dd-104">각 `catch` 블록은 예외 형식을 포함하고 해당 예외 형식을 처리하는 데 필요한 추가 명령문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-104">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="9e6dd-105">다음 예제에서 <xref:System.IO.StreamReader>는 *data.txt*라는 파일을 열고 해당 파일에서 줄을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-105">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="9e6dd-106">코드는 세 가지 예외 중 하나를 throw할 수 있으므로 `try` 블록에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-106">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="9e6dd-107">세 개 `catch` 블록이 예외를 catch하고 콘솔에 결과를 표시하여 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-107">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="9e6dd-108">CLR(공용 언어 런타임)은 `catch` 블록에서 처리되지 않은 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-108">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="9e6dd-109">CLR에서 예외를 catch하는 경우 CLR 구성에 따라 다음 결과 중 하나가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-109">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="9e6dd-110">**디버그** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-110">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="9e6dd-111">프로그램이 실행을 중지하고 예외 정보가 포함된 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-111">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="9e6dd-112">오류가 [표준 오류 출력 스트림](xref:System.Console.Error)으로 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-112">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="9e6dd-113">대부분의 코드가 예외를 throw할 수 있고, <xref:System.OutOfMemoryException>과 같은 일부 예외는 언제든지 CLR에서 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-113">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="9e6dd-114">애플리케이션은 이러한 예외를 처리할 필요가 없지만 다른 사용자가 사용할 라이브러리를 작성하는 경우 이러한 가능성에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-114">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="9e6dd-115">`try` 블록에서 코드를 설정하는 경우에 대한 제안 사항은 [예외에 대한 모범 사례](best-practices-for-exceptions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e6dd-115">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e6dd-116">참조</span><span class="sxs-lookup"><span data-stu-id="9e6dd-116">See also</span></span>

- [<span data-ttu-id="9e6dd-117">예외</span><span class="sxs-lookup"><span data-stu-id="9e6dd-117">Exceptions</span></span>](index.md)
- [<span data-ttu-id="9e6dd-118">.NET에서 I/O 오류 처리</span><span class="sxs-lookup"><span data-stu-id="9e6dd-118">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
