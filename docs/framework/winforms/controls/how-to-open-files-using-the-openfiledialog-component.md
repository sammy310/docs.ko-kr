---
title: '방법: OpenFile Dialog 구성 요소를 사용하여 파일 열기'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182127"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>방법: OpenFile Dialog를 사용하여 파일 열기

<xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> 파일을 검색하고 선택하기 위한 Windows 대화 상자가 구성 요소입니다. 선택한 파일을 열고 읽으려면 메서드를 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> 사용하거나 <xref:System.IO.StreamReader?displayProperty=nameWithType> 클래스의 인스턴스를 만들 수 있습니다. 다음 예제는 두 가지 방법을 모두 보여 주며 두 가지 방법을 보여 주습니다.

.NET Framework에서 <xref:System.Windows.Forms.FileDialog.FileName%2A> 속성을 얻거나 설정하려면 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> 클래스에서 부여한 권한 수준이 필요합니다. 예제에서는 <xref:System.Security.Permissions.FileIOPermission> 권한 검사를 실행 하 고 부분 신뢰 컨텍스트에서 실행 하는 경우 부족 한 권한으로 인해 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 을](../../misc/code-access-security-basics.md)참조하십시오.

이러한 예제를 C# 또는 Visual Basic 명령줄에서 .NET Framework 앱으로 빌드하고 실행할 수 있습니다. 자세한 내용은 [csc.exe를 가진 명령줄 건물](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드를](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)참조하십시오.

.NET Core 3.0부터 .NET Core 양식 * \<폴더 이름>.csproj* 프로젝트 파일이 있는 폴더에서 Windows .NET Core 앱으로 예제를 빌드하고 실행할 수도 있습니다.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>예: StreamReader를 통해 파일을 스트림으로 읽기  
  
다음 예제에서는 Windows <xref:System.Windows.Forms.Button> Forms 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용 하 여 <xref:System.Windows.Forms.OpenFileDialog> 메서드를 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 엽니다. 사용자가 파일을 선택하고 **확인을**선택하면 클래스의 인스턴스가 <xref:System.IO.StreamReader> 파일을 읽고 해당 내용을 양식의 텍스트 상자에 표시합니다. 파일 스트림에서 읽기에 대한 자세한 <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>내용은 및 을 참조하십시오.  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>예: OpenFile을 통해 필터링된 선택 항목에서 파일 열기

다음 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 <xref:System.Windows.Forms.OpenFileDialog> 사용하여 텍스트 파일만 표시하는 필터를 사용하여 을 엽니다. 사용자가 텍스트 파일을 선택하고 **확인을**선택하면 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 이 메서드가 메모장에서 파일을 여는 데 사용됩니다.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.OpenFileDialog>
- [오픈파일디아로그 구성 요소](openfiledialog-component-windows-forms.md)
