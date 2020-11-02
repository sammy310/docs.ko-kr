---
title: '방법: 새로 만든 데이터 파일 읽기 및 쓰기'
description: .NET에서 System.IO.BinaryReader 및 System.IO.BinaryWriter 클래스를 사용하여 새로 생성된 데이터 파일에 읽고 쓰는 방법을 알아봅니다.
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET], reading data
- I/O [.NET], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 236d50260efa66f21db6d0abba6cc5c258a74d8d
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188733"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>방법: 새로 만든 데이터 파일 읽기 및 쓰기

<xref:System.IO.BinaryWriter?displayProperty=nameWithType>와 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 클래스는 문자열이 아닌 데이터를 쓰고 읽는 데 사용됩니다. 다음 예제에서는 빈 파일 스트림을 만들어서 여기에 데이터를 쓰고 데이터를 읽는 방법을 보여줍니다.

이 예제는 현재 디렉터리에 *Test.data* 라는 데이터 파일을 만들고, 연결된 <xref:System.IO.BinaryWriter> 및 <xref:System.IO.BinaryReader> 개체를 만들고, <xref:System.IO.BinaryWriter> 개체를 사용하여 *Test.data* 에 0부터 10까지 정수를 씁니다. 이렇게 하면 파일 포인터가 파일 끝에 옵니다. <xref:System.IO.BinaryReader> 개체는 파일 포인터를 다시 원점으로 설정하고, 지정된 내용을 읽습니다.  
  
> [!NOTE]
> 현재 디렉터리에 *Test.data* 가 이미 있는 경우, <xref:System.IO.IOException> 예외가 throw됩니다. 예외를 throw하지 않고 항상 새 파일을 만들려면 <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>보다는 <xref:System.IO.FileMode.Create?displayProperty=nameWithType> 파일 모드 옵션을 사용합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a>참조

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [방법: 디렉터리 및 파일 열거](how-to-enumerate-directories-and-files.md)  
- [방법: 로그 파일 열기 및 추가](how-to-open-and-append-to-a-log-file.md)  
- [방법: 파일에서 텍스트 읽기](how-to-read-text-from-a-file.md)  
- [방법: 파일에 텍스트 쓰기](how-to-write-text-to-a-file.md)  
- [방법: 문자열에서 문자 읽기](how-to-read-characters-from-a-string.md)  
- [방법: 문자열에 문자 쓰기](how-to-write-characters-to-a-string.md)  
- [파일 및 스트림 I/O](index.md)
