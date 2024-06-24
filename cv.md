Nataliya Mun
Contact Info:
Phone: +7 (776) 181 44 44
E-mail: nataliya.moon@gmail.com
GitHub: NataliyaMoon
Telegram @NataliyaMoon

About Me
I am 32 years old, I work as a journalist. I want to learn programming because I think it will allow me to earn more and better reveal my mental potential.
Skills
HTML
CSS (Bootstrap, SASS/SCSS, BEM)
JavaScript
TypeScript
Git/GitHub
React

Code Examples
const Login = () => {
    const error = useSelector(({usersState}) => usersState.loginError);
    const dispatch = useDispatch();
    const navigate = useNavigate();
    const [state, setState] = useState({
        username: "",
        password: ""
    });

    const location = useLocation();
    useEffect(() => {
        dispatch(setLoginError(null));
    }, [location]);

    const inputChangeHandler = (e) => {
        const {name, value} = e.currentTarget;
        setState(prevState => {
            return {...prevState, [name]: value};
        });
    };

Education
KazNU (journalism, master's degree)
Attractor-school (JS)

Languages
Russian - native speaker
English - Pre-Intermediate
