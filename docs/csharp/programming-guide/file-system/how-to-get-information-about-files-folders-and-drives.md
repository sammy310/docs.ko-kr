---
title: 파일, 폴더 및 드라이브에 대한 정보를 가져오는 방법 - C# 프로그래밍 가이드
description: 파일, 폴더 및 드라이브에 대한 정보를 가져오는 방법을 알아봅니다. 코드 예제 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: f696cd90f197bede1a64949d211a563ce9a18376
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299931"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="5d300-104">파일, 폴더 및 드라이브에 대한 정보를 가져오는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5d300-104">How to get information about files, folders, and drives  (C# Programming Guide)</span></span>
<span data-ttu-id="5d300-105">.NET에서 다음 클래스를 사용하여 파일 시스템 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-105">In .NET, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="5d300-106"><xref:System.IO.FileInfo> 및 <xref:System.IO.DirectoryInfo> 클래스는 파일 또는 디렉터리를 나타내며, NTFS 파일 시스템에서 지원되는 많은 파일 특성을 노출하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-106">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="5d300-107">또한 파일 및 폴더를 열고, 닫고, 이동, 삭제하기 위한 메서드도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-107">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="5d300-108">파일, 폴더 또는 드라이브의 이름을 나타내는 문자열을 생성자에 전달하여 이러한 클래스의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-108">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="5d300-109"><xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType> 호출을 사용하여 파일, 폴더 또는 드라이브의 이름을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-109">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5d300-110"><xref:System.IO.Directory?displayProperty=nameWithType> 및 <xref:System.IO.File?displayProperty=nameWithType> 클래스는 디렉터리와 파일에 대한 정보를 가져오기 위한 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-110">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d300-111">예제</span><span class="sxs-lookup"><span data-stu-id="5d300-111">Example</span></span>  
 <span data-ttu-id="5d300-112">다음 예제에서는 파일 및 폴더에 대한 정보에 액세스하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-112">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="5d300-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5d300-113">Robust Programming</span></span>  
 <span data-ttu-id="5d300-114">사용자 지정 경로 문자열을 처리하는 경우 다음 조건에 대한 예외도 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-114">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="5d300-115">파일 이름 형식이 잘못된 경우.</span><span class="sxs-lookup"><span data-stu-id="5d300-115">The file name is malformed.</span></span> <span data-ttu-id="5d300-116">예를 들어 잘못된 문자를 포함하거나 공백만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-116">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="5d300-117">파일 이름이 null인 경우</span><span class="sxs-lookup"><span data-stu-id="5d300-117">The file name is null.</span></span>  
  
- <span data-ttu-id="5d300-118">파일 이름이 시스템에 정의된 최대 길이보다 긴 경우</span><span class="sxs-lookup"><span data-stu-id="5d300-118">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="5d300-119">파일 이름에 콜론(:)이 포함된 경우</span><span class="sxs-lookup"><span data-stu-id="5d300-119">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="5d300-120">애플리케이션에 지정된 파일을 읽을 수 있는 권한이 없는 경우 `Exists` 메서드는 경로가 있는지 여부에 관계없이 `false`를 반환합니다. 이 메서드는 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d300-120">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d300-121">참조</span><span class="sxs-lookup"><span data-stu-id="5d300-121">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="5d300-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5d300-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5d300-123">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5d300-123">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
