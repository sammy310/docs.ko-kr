---
description: '자세한 정보: 방법: Visual Basic에서 이진 파일 쓰기'
title: '방법: 이진 파일에 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: a1fe18c9143c26fd40e6a1d9cde36581c2c0be12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797330"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="34487-103">방법: Visual Basic에서 이진 파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="34487-103">How to: Write to Binary Files in Visual Basic</span></span>

<span data-ttu-id="34487-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> 메서드는 이진 파일에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="34487-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="34487-105">`append` 매개 변수가 `True`이면 파일에 데이터를 추가합니다. 그렇지 않으면 파일의 데이터를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="34487-105">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>

<span data-ttu-id="34487-106">파일 이름을 제외한 지정된 경로가 잘못된 경우 <xref:System.IO.DirectoryNotFoundException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="34487-106">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="34487-107">경로가 유효하지만 파일이 없는 경우 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="34487-107">If the path is valid but the file does not exist, the file will be created.</span></span>

## <a name="to-write-to-a-binary-file"></a><span data-ttu-id="34487-108">이진 파일에 쓰려면</span><span class="sxs-lookup"><span data-stu-id="34487-108">To write to a binary file</span></span>

<span data-ttu-id="34487-109">파일 경로 및 이름과 쓸 바이트를 제공하여 `WriteAllBytes` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34487-109">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="34487-110">이 예제에서는 `CollectedData.dat`라는 파일에 데이터 배열 `CustomerData`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34487-110">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a><span data-ttu-id="34487-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="34487-111">Robust Programming</span></span>

<span data-ttu-id="34487-112">다음 조건에서는 예외가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34487-112">The following conditions may create an exception:</span></span>

- <span data-ttu-id="34487-113">길이가 0인 문자열이거나, 공백으로만 구성되거나, 잘못된 문자를 포함하는 경우 등의 이유로 경로가 유효하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="34487-113">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="34487-114">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="34487-114">(<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="34487-115">경로가 `Nothing` 이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="34487-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="34487-116">`File`이 존재하지 않는 경로를 가리키는 경우(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="34487-116">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="34487-117">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="34487-117">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="34487-118">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="34487-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="34487-119">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="34487-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="34487-120">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="34487-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="34487-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34487-121">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="34487-122">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="34487-122">How to: Write Text to Files</span></span>](how-to-write-text-to-files.md)
