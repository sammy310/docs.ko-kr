---
title: '방법: 입력 마스크 설정'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: ac747bf46c4dd1451e58615b1ec0311d75c899e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760484"
---
# <a name="how-to-set-the-input-mask"></a>방법: 입력 마스크 설정
마스킹된 텍스트 상자 컨트롤에는 수락 하거나 거부 하는 사용자 입력에 대 한 선언적 구문을 지 원하는 향상 된 텍스트 상자 컨트롤이입니다. 마스크 속성을 설정 하면 응용 프로그램에 사용자 지정 유효성 검사 논리를 작성 하지 않고 허용 되는 사용자 입력을 지정할 수 있습니다. 자세한 내용은의 설명 섹션을 참조 하십시오.는 <xref:System.Windows.Forms.MaskedTextBox> 클래스입니다.  
  
## <a name="setting-the-mask-property-manually"></a>마스크 속성을 수동으로 설정  
 마스크 속성을 지 원하는 문자에 익숙한 경우 수동으로 입력할 수 있습니다. 마스크 속성을 지 원하는 문자 요약이의 설명 섹션을 참조 하세요.를 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
### <a name="to-set-the-mask-property-manually"></a>마스크 속성을 수동으로 설정 하려면  
  
1. **디자인** 뷰에서 select를 <xref:System.Windows.Forms.MaskedTextBox>.  
  
2. 에 **속성** 창 찾기는 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
3. 마스크를 입력 합니다. 예를 들어 `###`과 같이 입력합니다.  
  
## <a name="using-the-input-mask-dialog-box"></a>입력된 마스크 대화 상자를 사용 하 여  
 입력 마스크 대화 상자에서 일부 미리 정의 된 입력된 마스크를 제공합니다. 미리 정의 된 마스크를 변경 하거나 사용자 고유의 마스크를 수동으로 입력할 수도 있습니다.  
  
### <a name="to-open-the-input-mask-dialog-box"></a>입력 마스크 대화 상자를 열려면  
  
1. **디자인** 뷰에서 select를 <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1. 열려는 스마트 태그를 클릭 합니다 **MaskedTextBox 작업** 패널입니다.  
  
    2. 클릭 **마스크 설정**합니다.  
  
     \- 또는 -  
  
    1. 에 **속성** 창에서를 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.  
  
    2. 속성 값 열에서 줄임표 단추를 클릭 합니다.  
  
     합니다 **입력 마스크** 대화 상자가 나타납니다.  
  
### <a name="to-use-the-input-mask-dialog-box"></a>입력 마스크 대화 상자를 사용 하려면  
  
1. (선택 사항) 목록에서 미리 정의 된 면 중 하나를 클릭 합니다.  
  
2. (선택 사항) 미리 정의 된 마스크를 편집 합니다 **마스크** 상자입니다.  
  
3. (선택 사항) 에 새 마스크를 입력 합니다 **마스크** 상자입니다. 즉, 미리 정의 된 마스크 중 하나를 사용할 필요가 없습니다.  
  
    > [!NOTE]
    >  사용자에 게 표시 되는 문자를 표시 하는 미리 보기 상자는 <xref:System.Windows.Forms.MaskedTextBox>합니다. 이러한 문자는 사용자가 데이터를 올바르게 입력 수 있는 안내 합니다.  
  
4. 선택 하거나 선택을 취소 합니다 **사용 하 여 ValidatingType** 확인란 합니다. 합니다 **사용 하 여 ValidatingType** 확인란 사용자가 데이터 입력을 확인 하는 데이터 형식 사용 되는지 여부를 지정 합니다. 자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성을 참조하세요.  
  
5. **확인**을 클릭합니다.  
  
     마스크에 입력 합니다 **마스크** 속성에는 **속성** 창입니다.  
  
## <a name="see-also"></a>참고자료

- [연습: MaskedTextBox 컨트롤 사용](walkthrough-working-with-the-maskedtextbox-control.md)
