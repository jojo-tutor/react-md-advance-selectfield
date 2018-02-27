const {
  Autocomplete,
  Avatar,
  Badge,
  BottomNavigation,
  Button,
  Card,
  CardActions,
  CardTitle,
  CardText,
  Chip,
  DataTable,
  TableHeader,
  TableBody,
  TableRow,
  TableColumn,
  TablePagination,
  EditDialogColumn,
  SelectFieldColumn,
  MenuButtonColumn,
  DropdownMenuColumn,
  TableCardHeader,
  DialogContainer,
  Dialog,
  Divider,
  Drawer,
  ExpansionPanel,
  ExpansionList,
  FileInput,
  FileUpload,
  FontIcon,
  Grid,
  GridList,
  Cell,
  AccessibleFakeButton,
  AccessibleFakeInkedButton,
  Collapse,
  FocusContainer,
  Layover,
  IconSeparator,
  Portal,
  ResizeObserver,
  injectInk,
  List,
  ListItem,
  ListItemControl,
  Media,
  MediaOverlay,
  Menu,
  DropdownMenu,
  MenuButton,
  NavigationDrawer,
  Paper,
  DatePicker,
  TimePicker,
  CircularProgress,
  LinearProgress,
  SelectionControl,
  SelectionControlGroup,
  Checkbox,
  Radio,
  Switch,
  SelectField,
  Slider,
  Snackbar,
  SVGIcon,
  Subheader,
  TabsContainer,
  Tabs,
  Tab,
  MenuTab,
  TabPanel,
  TextField,
  Toolbar,
  injectTooltip,
  Tooltipped,
  Version,
  bem,
} = ReactMD;


const App = () => (
  <NavigationDrawer drawerTitle={`react-md@${Version}`} toolbarTitle="react-md Issue Template">
    <SampleSelectFields />
  </NavigationDrawer>
);

const roles = ['Admin', 'User', 'Guest']

const states = [
  { text: 'Alabama', value: 'AL' },
  { text: 'California', value: 'CA' },
  { text: 'Florida', value: 'FL' },
  { text: 'Hawaii', value: 'HI' }
]

class SampleSelectFields extends React.PureComponent {
  constructor(props) {
    super(props)
     this.state = {
       role: '',
       state: ''
     }
  }
  handleChange(key, value) {
    this.setState({ [key]: value })
  }
  render () {
    const { role, state } = this.state
    return (
      <Card className="demo">
        <CardTitle title="Sample Demo" />
        <CardText>
         <AdvanceSelectField
          key='role'
          id='role'
          label='Select role: (menu as array of strings)'
          menuItems={roles}
          className='md-cell md-cell--12 dropdown_menu blank-left-icon'
          position={SelectField.Positions.BELOW}
          value={role}
          onChange={this.handleChange.bind(this, 'role')}
        />
        <AdvanceSelectField
          key='state'
          id='state'
          label='Select state: (menu as array of objects)'
          menuItems={states}
          itemLabel='text'
          itemValue='value'
          className='md-cell md-cell--12 dropdown_menu blank-left-icon'
          position={SelectField.Positions.BELOW}
          value={state}
          onChange={this.handleChange.bind(this, 'state')}
        />
          <div>Selected role:
            <br/>
            <strong>{role}</strong>
          </div>
          <br/>
          <div>Selected state:
            <br/>
            <strong>{state}</strong>
          </div>
        </CardText>
      </Card>
    )
  }
}

class AdvanceSelectField extends React.PureComponent {
  constructor(props) {
    super(props)
    this.ref = null
  }
  handleBlur() {
    const { id, onChange, value: propsValue } = this.props
    const { state, props } = this.ref
    const { activeIndex } = state
    const { menuItems, itemValue } = props
    const isObject = menuItems.length && typeof menuItems[0] === 'object'
    const value = (activeIndex > -1)
      ? isObject ? menuItems[activeIndex][itemValue] : menuItems[activeIndex]
      : null
    
    if (value && propsValue !== value) {
      props.value = value
      onChange(value)
    }
  }
  render() {
    return (
      <SelectField
        ref={ref => this.ref = ref}
        onBlur={() => this.handleBlur()}
        {...this.props}
      />
    )
  }
}


ReactDOM.render(<App />, document.getElementById('app'));
