---
title: '방법: 디렉터리 복사'
description: 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 I/O 클래스를 사용하여 디렉터리를 복사하는 방법을 참조하세요.
ms.date: 12/27/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: dfe45d8529eb927a6b174a7bb411afa8072035f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679067"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="b14aa-103">방법: 디렉터리 복사</span><span class="sxs-lookup"><span data-stu-id="b14aa-103">How to: Copy directories</span></span>

<span data-ttu-id="b14aa-104">이 문서에서는 I/O 클래스를 사용하여 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b14aa-104">This article demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="b14aa-105">비동기 파일 복사의 예제는 [비동기 파일 I/O](asynchronous-file-i-o.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b14aa-105">For an example of asynchronous file copy, see [Asynchronous file I/O](asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="b14aa-106">이 예제는 `DirectoryCopy` 메서드의 `copySubDirs`를 `true`로 설정하여 하위 디렉터리를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b14aa-106">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="b14aa-107">`DirectoryCopy` 메서드는 더 이상 복사할 항목이 없을 때까지 각 하위 디렉터리에서 자신을 호출하여 하위 디렉터리를 재귀적으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b14aa-107">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b14aa-108">예제</span><span class="sxs-lookup"><span data-stu-id="b14aa-108">Example</span></span>  

 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="b14aa-109">참조</span><span class="sxs-lookup"><span data-stu-id="b14aa-109">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="b14aa-110">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="b14aa-110">File and stream I/O</span></span>](index.md)
- [<span data-ttu-id="b14aa-111">공통 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="b14aa-111">Common I/O tasks</span></span>](common-i-o-tasks.md)
- [<span data-ttu-id="b14aa-112">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="b14aa-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)
