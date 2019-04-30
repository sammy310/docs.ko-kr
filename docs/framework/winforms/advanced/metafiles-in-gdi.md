---
title: GDI+의 메타파일
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: bb972f158496192aa38f10564209bb2781837414
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010033"
---
# <a name="metafiles-in-gdi"></a>GDI+의 메타파일
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 제공 된 <xref:System.Drawing.Imaging.Metafile> 클래스를 기록 하 고 메타 파일을 표시할 수 있도록 합니다. 벡터 이미지 라고도 불리는 메타 파일 이미지 그리기 명령 및 설정의 시퀀스로 저장 되어 있는 경우 명령 및 설정에 기록를 <xref:System.Drawing.Imaging.Metafile> 개체를 메모리에 저장 하거나 파일 또는 스트림에 저장할 수 있습니다.  
  
## <a name="metafile-formats"></a>메타 파일 형식  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 다음 형식으로 저장 된 메타 파일을 표시할 수 있습니다.  
  
- Windows 메타 파일 (WMF)  
  
- EMF(확장 메타파일)  
  
- EMF+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] EMF, EMF + 형식으로 있지만 WMF 형식이 메타 파일을 기록할 수 있습니다.  
  
 EMF +는 EMF 수 있도록 하려면 확장 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드를 저장 합니다. EMF + 형식에 두 가지 변형이 있습니다. EMF +만 및 EMF + 복합 합니다. EMF + 전용 메타 파일 포함 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 레코드입니다. 이러한 메타 파일은 표시할 수 있습니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 하지 않습니다 하지만 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다. EMF + 복합 메타 파일 포함 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 고 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다. 각 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] EMF + 복합 레코드 메타 파일 쌍을 이룹니다 대체를 사용 하 여 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 레코드입니다. 이러한 메타 파일은 표시할 수 있습니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 또는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.  
  
 다음 예제에서는 이전에 파일로 저장 된 메타 파일을 표시 합니다. 메타 파일에서 왼쪽 위 모퉁이 표시 됩니다 (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>참고자료

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
