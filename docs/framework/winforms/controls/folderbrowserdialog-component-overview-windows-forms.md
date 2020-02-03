---
title: FolderBrowserDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745733"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>FolderBrowserDialog 구성 요소 개요(Windows Forms)

Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소는 폴더를 검색 하 고 선택 하는 데 사용 되는 모달 대화 상자입니다. <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소 내에서 새 폴더를 만들 수도 있습니다.

> [!NOTE]
> 폴더 대신 파일을 선택 하려면 [OpenFileDialog](openfiledialog-component-windows-forms.md) 구성 요소를 사용 합니다.

<xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용 하 여 런타임에 표시 됩니다. <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 속성을 설정 하 여 대화 상자의 트리 뷰 내에 표시 되는 최상위 폴더와 하위 폴더를 확인 합니다. 대화 상자가 표시 되 면 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성을 사용 하 여 선택한 폴더의 경로를 가져올 수 있습니다.

폼에 추가 되 면 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소가 Visual Studio의 Windows Forms 디자이너 아래쪽에 있는 트레이에 표시 됩니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [FolderBrowserDialog 구성 요소](folderbrowserdialog-component-windows-forms.md)
