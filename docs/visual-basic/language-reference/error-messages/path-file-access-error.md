---
title: 경로-파일 액세스 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 70de8f9cb33ab3d889f4916ae3d5de48cd218092
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871194"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="af436-102">경로/파일 액세스 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="af436-102">Path/File access error</span></span>

<span data-ttu-id="af436-103">파일 액세스 또는 디스크 액세스 작업 중에 운영 체제에서 경로와 파일 이름 간에 연결을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af436-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af436-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="af436-104">To correct this error</span></span>  
  
1. <span data-ttu-id="af436-105">파일 사양의 형식이 올바르게 지정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="af436-106">파일 이름에는 정규화 된 절대 경로 또는 상대 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af436-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="af436-107">정규화 된 경로는 드라이브 이름 (경로가 다른 드라이브에 있는 경우)으로 시작 하 여 루트에서 파일로의 명시적 경로를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="af436-108">정규화 되지 않은 경로는 현재 드라이브와 디렉터리에 대 한 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="af436-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="af436-109">기존 읽기 전용 파일을 대체 하는 파일을 저장 하려고 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="af436-110">이 경우 대상 파일의 읽기 전용 특성을 변경 하거나 파일을 다른 파일 이름으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="af436-111">읽기 전용 파일을 순차적 또는 모드로 열지 않았는지 확인 `Output` `Append` 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="af436-112">이 경우 모드에서 파일을 열거나 `Input` 파일의 읽기 전용 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="af436-113">데이터베이스 또는 문서 내의 Visual Basic 프로젝트를 변경 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af436-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af436-114">참조</span><span class="sxs-lookup"><span data-stu-id="af436-114">See also</span></span>

- [<span data-ttu-id="af436-115">오류 형식</span><span class="sxs-lookup"><span data-stu-id="af436-115">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
