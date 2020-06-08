---
title: '방법: 디렉터리 복사'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: f71f428037f33fdbc692ca2f02a4c767998d684e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288578"
---
# <a name="how-to-copy-directories"></a>방법: 디렉터리 복사
이 항목에서는 I/O 클래스를 사용하여 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 방법을 보여줍니다.

비동기 파일 복사의 예제는 [비동기 파일 I/O](asynchronous-file-i-o.md)을 참조하세요.

이 예제는 `DirectoryCopy` 메서드의 `copySubDirs`를 `true`로 설정하여 하위 디렉터리를 복사합니다. `DirectoryCopy` 메서드는 더 이상 복사할 항목이 없을 때까지 각 하위 디렉터리에서 자신을 호출하여 하위 디렉터리를 재귀적으로 복사합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>참조

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [파일 및 스트림 I/O](index.md)
- [공통 I/O 작업](common-i-o-tasks.md)
- [비동기 파일 I/O](asynchronous-file-i-o.md)
