---
title: '방법: 사용 하 여 적중 테스트 영역'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: a9435724e7674fd196ad70bdfd0ab43808a53058
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709748"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>방법: 사용 하 여 적중 테스트 영역
적중 횟수 테스트의 목적은 커서 아이콘 단추 등의 지정 된 개체에 대해 인지 여부를 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 사각형 영역을 결합 하 여 더하기 모양의 영역을 만듭니다. 가정 변수의 `point` 최신 클릭의 위치를 저장 합니다. 코드 확인 여부를 `point` 더하기 모양의 지역에 있습니다. 요점은 (적중) 지역의 경우 지역 불투명 빨강 브러시를 사용 하 여 채워집니다. 그렇지 않으면 지역 빨간색 반투명 브러시를 사용 하 여 채워집니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Drawing.Region>
- [GDI+의 영역](regions-in-gdi.md)
- [방법: 클리핑 영역 사용](how-to-use-clipping-with-a-region.md)
