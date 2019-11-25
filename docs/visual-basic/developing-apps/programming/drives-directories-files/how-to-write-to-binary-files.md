---
title: '방법: 이진 파일에 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 72d019f5f49868bd84d0507535e8ebc547b50e25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334426"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="82fc5-102">방법: Visual Basic에서 이진 파일 쓰기</span><span class="sxs-lookup"><span data-stu-id="82fc5-102">How to: Write to Binary Files in Visual Basic</span></span>

<span data-ttu-id="82fc5-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> 메서드는 이진 파일에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="82fc5-104">`append` 매개 변수가 `True`이면 파일에 데이터를 추가합니다. 그렇지 않으면 파일의 데이터를 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>

<span data-ttu-id="82fc5-105">파일 이름을 제외한 지정된 경로가 잘못된 경우 <xref:System.IO.DirectoryNotFoundException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="82fc5-106">경로가 유효하지만 파일이 없는 경우 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-106">If the path is valid but the file does not exist, the file will be created.</span></span>

## <a name="to-write-to-a-binary-file"></a><span data-ttu-id="82fc5-107">이진 파일에 쓰려면</span><span class="sxs-lookup"><span data-stu-id="82fc5-107">To write to a binary file</span></span>

<span data-ttu-id="82fc5-108">파일 경로 및 이름과 쓸 바이트를 제공하여 `WriteAllBytes` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="82fc5-109">이 예제에서는 `CollectedData.dat`라는 파일에 데이터 배열 `CustomerData`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>

[!code-vb[VbVbcnMyFileSystem#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#27)]

## <a name="robust-programming"></a><span data-ttu-id="82fc5-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="82fc5-110">Robust Programming</span></span>

<span data-ttu-id="82fc5-111">다음 조건에서는 예외가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82fc5-111">The following conditions may create an exception:</span></span>

- <span data-ttu-id="82fc5-112">길이가 0인 문자열이거나, 공백으로만 구성되거나, 잘못된 문자를 포함하는 경우 등의 이유로 경로가 유효하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="82fc5-112">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="82fc5-113">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="82fc5-113">(<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="82fc5-114">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="82fc5-115">`File`이 존재하지 않는 경로를 가리키는 경우(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-115">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>

- <span data-ttu-id="82fc5-116">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-116">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="82fc5-117">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="82fc5-118">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-118">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="82fc5-119">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="82fc5-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

## <a name="see-also"></a><span data-ttu-id="82fc5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82fc5-120">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="82fc5-121">방법: 파일에 텍스트 쓰기</span><span class="sxs-lookup"><span data-stu-id="82fc5-121">How to: Write Text to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
