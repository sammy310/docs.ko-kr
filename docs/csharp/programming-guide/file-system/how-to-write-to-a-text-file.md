---
title: '방법: 텍스트 파일에 쓰기 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: d08fe23f2dbfe46c0a58084b05610dfe7db3dda9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589925"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="0a99e-102">방법: 텍스트 파일에 쓰기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0a99e-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="0a99e-103">다음 코드 예제에서는 파일에 텍스트를 쓰는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="0a99e-104">처음 두 예에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스의 정적 편의 메서드를 사용하여 `IEnumerable<string>`의 각 요소와 문자열을 텍스트 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="0a99e-105">예제 3에서는 파일에 쓸 때 각 줄을 개별적으로 처리해야 하는 경우 파일에 텍스트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="0a99e-106">예제 1-3에서는 파일의 기존 내용을 모두 덮어쓰지만 예제 4에서는 기존 파일에 텍스트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="0a99e-107">이 예에서는 파일에 모든 문자열 리터럴을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-107">These examples all write string literals to files.</span></span> <span data-ttu-id="0a99e-108">파일에 작성된 텍스트의 서식을 지정하려면 <xref:System.String.Format%2A> 메서드 또는 C# [문자열 보간](../../language-reference/tokens/interpolated.md) 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a99e-109">예</span><span class="sxs-lookup"><span data-stu-id="0a99e-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0a99e-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0a99e-110">Robust Programming</span></span>  
 <span data-ttu-id="0a99e-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0a99e-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="0a99e-112">파일이 있지만 읽기 전용인 경우</span><span class="sxs-lookup"><span data-stu-id="0a99e-112">The file exists and is read-only.</span></span>  
  
- <span data-ttu-id="0a99e-113">경로 이름이 너무 긴 경우</span><span class="sxs-lookup"><span data-stu-id="0a99e-113">The path name may be too long.</span></span>  
  
- <span data-ttu-id="0a99e-114">디스크가 꽉 찬 경우</span><span class="sxs-lookup"><span data-stu-id="0a99e-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a99e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a99e-115">See also</span></span>

- [<span data-ttu-id="0a99e-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0a99e-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0a99e-117">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0a99e-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="0a99e-118">샘플: 애플리케이션 스토리지에 컬렉션 저장</span><span class="sxs-lookup"><span data-stu-id="0a99e-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
