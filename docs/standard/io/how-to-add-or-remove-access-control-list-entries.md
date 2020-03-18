---
title: '방법: 액세스 제어 목록 항목 추가 또는 제거(.NET Framework에만 해당)'
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: 5f41c518b8732adff95593cab29d7085adcc9ab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708130"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a><span data-ttu-id="6ca91-102">방법: 액세스 제어 목록 항목 추가 또는 제거(.NET Framework에만 해당)</span><span class="sxs-lookup"><span data-stu-id="6ca91-102">How to: Add or remove Access Control List entries (.NET Framework only)</span></span>
<span data-ttu-id="6ca91-103">파일 또는 디렉터리에서 ACL(액세스 제어 목록) 항목을 추가 또는 제거하려면, 파일 또는 디렉터리에서 <xref:System.Security.AccessControl.FileSecurity> 또는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-103">To add or remove Access Control List (ACL) entries to or from a file or directory, get the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object from the file or directory.</span></span> <span data-ttu-id="6ca91-104">개체를 수정한 다음, 파일이나 디렉터리에 다시 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-104">Modify the object, and then apply it back to the file or directory.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="6ca91-105">파일에서 ACL 항목 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6ca91-105">Add or remove an ACL entry from a file</span></span>  
  
1. <span data-ttu-id="6ca91-106"><xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> 메서드를 호출하여 파일의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.FileSecurity> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-106">Call the <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2. <span data-ttu-id="6ca91-107">1단계에서 반환된 <xref:System.Security.AccessControl.FileSecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-107">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="6ca91-108">변경 내용을 적용하려면 <xref:System.Security.AccessControl.FileSecurity> 개체를 <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-108">To apply the changes, pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="6ca91-109">디렉터리에서 ACL 항목 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="6ca91-109">Add or remove an ACL entry from a directory</span></span>  
  
1. <span data-ttu-id="6ca91-110"><xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> 메서드를 호출하여 디렉터리의 현재 ACL 항목을 포함하는 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-110">Call the <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2. <span data-ttu-id="6ca91-111">1단계에서 반환된 <xref:System.Security.AccessControl.DirectorySecurity> 개체에서 ACL 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-111">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="6ca91-112">변경 내용을 적용하려면 <xref:System.Security.AccessControl.DirectorySecurity> 개체를 <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-112">To apply the changes, pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ca91-113">예제</span><span class="sxs-lookup"><span data-stu-id="6ca91-113">Example</span></span>  
 <span data-ttu-id="6ca91-114">이 예제를 실행하려면 유효한 사용자 또는 그룹 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-114">You must use a valid user or group account to run this example.</span></span> <span data-ttu-id="6ca91-115">예제에서는 <xref:System.IO.File> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-115">The example uses a <xref:System.IO.File> object.</span></span> <span data-ttu-id="6ca91-116"><xref:System.IO.FileInfo>, <xref:System.IO.Directory> 및 <xref:System.IO.DirectoryInfo> 클래스에 동일한 프로시저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca91-116">Use the same procedure for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
