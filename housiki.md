�E�V�X�e�������݌v���쐬
��Spring���傩�甲��
�@-Web�A�v���P�[�V�����J������
�@�@SpringMVC�̃A�[�L�e�N�`��
�@�@��ʑJ��

�ADI�Ƃ́H
�@DI�i�ˑ����̒����j�́A�\�t�g�E�F�A�̃f�U�C���p�^�[����1�ŁA�uInversion of Control Principle�i����̔��]�̌����j�v���������܂��B
DI��p���邱�ƂŁA�R���|�[�l���g���\������C���X�^���X�̐����ƈˑ��֌W�̉������\�[�X�R�[�h���番�����邱�Ƃ��ł��܂��B
���̋@�\��DI�R���e�i���񋟂��܂��B
�@DI�R���e�i�𗘗p����ƁA����܂Œ��ڃC���X�^���X�𐶐����Ă����A�v���P�[�V�����i�}�@�j��DI�R���e�i���o�R���ăC���X�^���X���擾
�ł���悤�ɂȂ�܂��i�A�j�B����ɁA���̎擾�����C���X�^���X�̒��ŗ��p����Ă���C���X�^���X��DI�R���e�i�ɊǗ�����A�ݒ�ςݏ�ԂŎ擾�ł��܂��B


�Q�D���̓`�F�b�N
�@�@Bean Validation
�@�@���A�m�e�[�V�����x�[�X�Ŏ�������
�@�@�E���b�Z�[�W�̕ύX���@
�@�@�@
�@�@�@application-messages_ja.properties

Spring MVC�ł̃f�t�H���g����ł́A�t�H�[���N���X�ɑ΂�����̓`�F�b�N�͎��s����܂���B���̓`�F�b�N���s���ꍇ�́A���̓`�F�b�N���s�����\�b�h��
�����Ƀt�H�[���N���X���`���āA@org.springframework.validation.annotation.Validated�܂���@javax.validation.Valid���w�肵�Ă��������B
@Validated���g�p�����Bean Validation�̎d�g�݂����p�ł��邽�߁A�{���C�ł�@Validated���g�p����O��Ő������܂��B

�E�R�[�h��

```
public String search(
	@Validated AccountSearchForm form,
	BindingResult result,
	Model model) {

}
�@���\�b�h�����Ƀt�H�[���N���X���`����@Validated���w�肷��
�A���̓`�F�b�N�Ώۂ̃t�H�[���N���X�̒����org.springframework.validation.BindingResutl���`����B
�@BindingResult�ɂ́A���N�G�X�g�f�[�^�̃o�C���f�B���O�G���[�Ɠ��̓`�F�b�N�G���[�̏�񂪊i�[�����B

�Q�D�P�D���̓`�F�b�N���ʂ̔�����@
���̓`�F�b�N�̎��s�Ɠ��̓`�F�b�N���ʁiBindingResult�j�̐����̓t���[�����[�N�������ōs���܂����A
���̓`�F�b�N���ʂ̃G���[���肨��уG���[�����́A�A�v���P�[�V�������Ŏ�������K�v������܂��B
���̓`�F�b�N���ʂ̔����BindingResult�̃��\�b�h���g�p���܂��B

�@�Z�b�V�������
�@�@Session�X�R�[�v�i�A�m�e�[�V�����j
�@�f�[�^�A�N�Z�X
�@�@�ESpring JDBC
�@�@�@RowMapper�͂Ȃ��AResultSet����Bean�ɓ]��
�@�@
�@�g�����U�N�V����
�@�@�����I�ȃg�����U�N�V����
�@�@�@TransactionManager�𗘗p����B

�@��O�n���h�����O
�@�@Exeption���p�A�쐬�Ȃ�
�@�@�E�r�W�l�X��O
�@�@�E����ғ����ɔ������郉�C�u������O
�@�@�E�V�X�e����O
�@�@�E�\�����Ȃ��V�X�e����O
�@�@�E�v���I�ȃG���[
�@�@�E���N�G�X�g�s�����ɔ�������t���[�����[�N��O

�@-Spring Test����
�@�e�X�g
�@�@JUnit�Acheckstyle�AFindBug�A
�@-Spring Security����
�@Spring Security�̓���


�E�V�X�e�������݌v���̏C��
�@�E�A�v���P�[�V���������i���O�ɗp�ӂ��Ă���N���X�̐����j
�@�@JSF��SpringBoot�iSpringMVC�iWeb�j�AThymeleaf�AJPA�ALombok�j
�@�@Validation�F
�@�E�\�����ނ̈ꗗ


���A�v���P�[�V����
�@�P���[�X�P�[�X���A�v���P�[�V�����Ƃ��āA�P�ɃA�v���P�[�V�����ƕ\�L�����ꍇ�͌����Ƃ��ă��j���[����Ăяo���ꂽ�ȍ~���w���B

���A�v���P�[�V�����̍\��
�@�A�v���P�[�V�������\�����鎑�ނ��������
�@�{�A�v���P�[�V������Spring Framework�̒��ŁAWeb�A�v���P�[�V�������J�����邽�߂̃t���[�����[�N�ł���Spring MVC���̗p����B

�@�A�v���P�[�V�����̃A�[�L�e�N�`���Ƃ��Ă�MVC�p�^�[���̓A�N�V�����x�[�X�ƃR���|�[�l���g�x�[�X�̂Q�p�^�[��������A
Spring MVC��Struts�Ɠ������A�N�V�����x�[�X�̃t���[�����[�N�ł���B
�@�A�N�V�����x�[�X�t���[�����[�N�́A���N�G�X�g�ɂ���Ď��s���鏈���i�A�N�V�����j�����肵�A�����̌��ʂƂ��ă��X�|���X�iHTML�Ȃǁj
��Ԃ��܂��B

���t�����g�R���g���[���[��
Spring MVC�́u�t�����g�R���g���[���[�v�ƌĂ΂��A�[�L�e�N�`�����̗p���Ă���B�t�����g�R���g���[���[�p�^�[���́A�N���C�A���g�����
���N�G�X�g���t�����g�R���g���[���[�ƌĂ΂��R���|�[�l���g���󂯎��A���N�G�X�g�̓��e�ɉ����Ď��s����Handler��I������A�[�L�e�N�`��
�ƂȂ��Ă���B

�������t���[��}��

�t�����g�R���g���[���[�p�^�[���́A���ʓI�ȏ������t�����g�R���g���[���ɏW�񂷂邱�Ƃ��ł��邽�߁AHandler�ōs�����������炷���Ƃ��ł��܂��B
�t�����g�R���g���[���ł́A�ȉ��̏������s���Ă���B
�E�N���C�A���g����̃��N�G�X�g�̎�t
�E���N�G�X�g�f�[�^��Java�I�u�W�F�N�g�ւ̕ϊ�
�E���̓`�F�b�N�̎��s�iBean Validation�j
�EHandler�̌Ăяo��
�EView�̉���
�E�N���C�A���g�ւ̃��X�|���X�f�[�^�̉���
�E��O�n���h�����O

Spring MVC�̃A�[�L�e�N�`���ڍ�

�����t���[
Spring MVC�̃t�����g�R���g���[���́Aorg.springframework.web.servlet.DispatchrerServlet�N���X�i�T�[�u���b�g�j�Ƃ��Ď�������Ă���A
�ȉ��̂悤�ȗ���ŏ������s���B

�������t���[�}��

�@Dispatcherservlet�N���X�́A�N���C�A���g����̃��N�G�X�g���󂯕t����
�ADispatcherServlet�N���X�́AHandlerMapping�C���^�[�t�F�C�X��getHandler���\�b�h���Ăяo���A���N�G�X�g�������s��Handler�I�u�W�F�N�g�iController�j���擾����B
�BDispatcherServlet�N���X�́AHandlerAdapter�C���^�[�t�F�C�X��handle���\�b�h���Ăяo���AController�I�u�W�F�N�g�̃��\�b�h�Ăяo�����˗�����B
�CHandlerAdapter�C���^�[�t�F�C�X�̎����N���X�́AHandler�I�u�W�F�N�g�Ɏ�������Ă��郁�\�b�h���Ăяo���A���N�G�X�g���������s����B
�DController�́A�r�W�l�X���W�b�N�����s���A�������ʂ�Model�ɐݒ肵�A�r���[�̘_������HandlerAdapter�ɕԋp����B
�EDispatcherServlet�N���X�́AVireResolver�C���^�[�t�F�C�X��resolveVireName���\�b�h���Ăяo���AHandler�I�u�W�F�N�g����ԋp���ꂽView���ɑΉ�����View�C���^�[�t�F�C�X
�@�̃I�u�W�F�N�g���擾����B
�FDispatcherServlet�N���X��View�C���^�[�t�F�C�X��render���\�b�h���Ăяo���A���X�|���X�ւ̃����_�����O�����̎��s���˗�����BView�C���^�[�t�F�C�X�̎����N���X�́A
�@JSP�Ȃǂ̃e���v���[�g�G���W���Ȃǂ��g�p���ă����_�����O����f�[�^�𐶐�����B
�GDispatcherServlet�N���X�́A�N���C�A���g�փ��X�|���X��ԋp����B

���R���|�[�l���g�F���i�A����
���A�v���P�[�V�����̍쐬���@


