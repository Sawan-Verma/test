# test
test case for angular
describe('ContractRechargeListComponent', () => {
  let component: ContractRechargeListComponent;
  let fixture: ComponentFixture<ContractRechargeListComponent>;

  const mockData = {
    'prods:hasChanges': true,
    'eContRecharge': [
      {
        'prods:id': '12345',
        'OrgCode': '01',
        'ClientCode': 'HSG',
        'Contract': 'NERESP',
        'ResourceCode': 'LAB-CL-JOT2',
        'TaskCode': '101101',
        'Uplift': 11,
        'MergeOption': 'None',
        'SpecialOption': 'na',
        'RechargeFlag': 'No',
        'LineNo': 1,
        'id': '01|HSG|NERESP|1',
        'seq': 7,
        'prods:rowState': 'created'
      }
    ]
  };

  beforeEach(async(() => {
    TestBed.configureTestingModule({
      imports: [
        DropDownsModule,
        FormsModule,
        ReactiveFormsModule,
        GridModule,
        ButtonsModule,
        InputsModule,
        DialogModule,
        HttpModule
      ],
      providers: [ContractRechargeService, ],
      declarations: [ ContractRechargeListComponent, ResourceCodeSearchComponent, DeleteAlertComponent ]
    })
    .compileComponents();
  }));

  beforeEach(() => {
    fixture = TestBed.createComponent(ContractRechargeListComponent);
    component = fixture.componentInstance;
    component.createForm();
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });
  it('form invalid when empty', () => {
    expect(component.addRechargeForm.valid).toBeFalsy();
  });
  it('resourceCode field  validation', () => {
    let resourceCodeField = component.addRechargeForm['_value'].resourceCode;
    resourceCodeField = '';
    expect(resourceCodeField.valid).toBeFalsy();
  });
  it('lineNo field  validation', () => {
    let lineNoField = component.addRechargeForm['_value'].lineNo;
    lineNoField = '';
    expect(lineNoField.valid).toBeFalsy();
  });
  it('sor field  validation', () => {
    let sorField = component.addRechargeForm['_value'].upLift;
    sorField = '';
    expect(sorField.valid).toBeFalsy();
  });
  it('upLift field  validation', () => {
    let upLiftField = component.addRechargeForm['_value'].upLift;
    upLiftField = '';
    expect(upLiftField.valid).toBeFalsy();
  });
  it('rFlag field  validation', () => {
    let rFlagField = component.addRechargeForm['_value'].rFlag;
    rFlagField = '';
    expect(rFlagField.valid).toBeFalsy();
  });
});
